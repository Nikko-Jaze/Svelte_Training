<script>
    export let addItems;

    let myForm;

    const handleSubmit = ()=>{
        let formData = new FormData(myForm);

        addItems = Object.fromEntries(formData.entries());
        myForm.reset()
    }
</script>

<form on:submit|preventDefault={handleSubmit} bind:this={myForm}>
    <div class="row mt-3">
        <div class="col">
            <input class="form-control" name="name" type="text" placeholder="Car" required>
        </div>
        <div class="col">
            <input class="form-control" name="type" type="text" placeholder="Brand" required>
        </div>
        
    </div>
    <div class="row mt-3">
        <div class="d-grid gap-2 col-6 mx-auto">
            <button type="submit" class="btn btn-primary" >Add Car</button>
            </div>
    </div>
</form>
