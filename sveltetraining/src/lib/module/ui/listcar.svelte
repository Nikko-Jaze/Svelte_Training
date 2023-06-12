<script>
    export let category = [];
</script>
  

  <div class="row">
    <ul class="list-group">
        {#each category as category}
        <li class="list-group-item">
            <div class="d-flex align-items-center justify-content-between">
                
            {category.type} - {category.name}
               
            </div>
        </li>
        {/each}
      </ul>
</div>
  