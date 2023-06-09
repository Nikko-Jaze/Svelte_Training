<script>
    let brand = 'Car Brand';
    let category = [{brand:"Toyota",name:"Fortuner"},{brand:"Ford",name:"Everest"},{brand:"Nissan",name:"Terra"},{brand:"Mitsubishi",name:"Montero"}]

    
</script>

<div class="position relative">
    <div class="card position-absolute top-50 start-50 translate-middle">
        <div class="card-header">
          <strong>{brand}</strong>
        </div>
        
        <div class="card-body ">
            <div class="row">
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
            </div>
            <hr>
            <div class="row">
                <ul class="list-group">
                    {#each category as car}
                        <li class="list-group-item">{car.brand} - {car.name}</li>
                    {/each}
                    
                    
                  </ul>
            </div>
            
            <div class="row mt-3">
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
            </div>
        </div>
      </div>
</div>

