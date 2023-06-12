
<script>
    export let filters = [];
    export let selected = "";
    export let filterValue = "";
</script>

<div class="row">
    <div class="col">
        <label for="">Category</label>
    </div>

    <div class="col">
        <select bind:value={filterValue} id="filter" class="form-select" aria-label="Default select example" >
            <option value="">Car Brands</option>

            {#each filters  as filter}
            <option value={filter} selected={filter == selected}>{filter}</option>
            {/each}
            
          </select>
    </div>
</div>