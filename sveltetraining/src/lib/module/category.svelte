<script>
    import { onMount } from 'svelte';
    import Filter from "$lib/module/forms/car_brand.svelte";
    import List from "$lib/module/ui/listcar.svelte";
    import Add from "$lib/module/forms/add_car.svelte";
    import {category} from "$lib/module/store.js"
    

    let data = JSON.parse(JSON.stringify($category));
    let addItems;

    let filters = $category.map((details)=> {return details.type})
    let filterValue;

    //car filter
    $:{
      if(filterValue)
        data = $category.filter(data => data.type== filterValue)
    }

    //add car in store
    $:{
      if(addItems)
      {
        category.add(addItems)
        data     = JSON.parse(JSON.stringify($category));
        filters  = $category.map((details)=> {return details.type})
        addItems = null;
        saveData();
      }
    }

    function saveData() {
    localStorage.setItem('categoryData', JSON.stringify(category));
  }

  // Load data from localStorage on component mount
  onMount(() => {
    const storedData = localStorage.getItem('categoryData');
    if (storedData) {
      category.set(JSON.parse(storedData));
    }
  });

</script>

<div class="position relative">
    <div class="card position-absolute top-50 start-50 translate-middle">
        <div class="card-header">
          <strong>Car Brand</strong>
        </div>
        
        <div class="card-body ">
            <!-- <div class="row">
                <div class="col">
                    <label for="">Category</label>
                </div>

                <div class="col">
                    <select class="form-select" aria-label="Default select example">
                        <option selected>Select Car Brand</option>
                        <option value="1">One</option>
                        <option value="2">Two</option>
                        <option value="3">Three</option>
                      </select>
                </div>
            </div> -->
            <Filter bind:filters bind:filterValue />
            <hr>
            <!-- <div class="row">
                <ul class="list-group">
                    {#each category as car}
                        <li class="list-group-item">{car.brand} - {car.name}</li>
                    {/each}
                    
                    
                  </ul>
            </div> -->
            <List bind:category={data} />
            
            <!-- <div class="row mt-3">
                <div class="col">
                    <input class="form-control" type="text" placeholder="Car">
                </div>
                <div class="col">
                    <input class="form-control" type="text" placeholder="Brand">
                </div>
                
            </div>
            <div class="row mt-3">
                <div class="d-grid gap-2 col-6 mx-auto">
                    <button class="btn btn-primary" type="button">Add Car</button>
                    
                  </div>
            </div> -->
            <Add bind:addItems/>
        </div>
      </div>
</div>

