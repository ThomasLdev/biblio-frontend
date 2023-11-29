<script>
    import MainButton from "$ui/Button.svelte"

    export let data = data;
</script>

<div class="card card-side bg-base-100 shadow-xl lg:hover:drop-shadow-xl">
    <figure>
        <img src="https://daisyui.com/images/stock/photo-1635805737707-575885ab0820.jpg" alt="Movie"/>
    </figure>
    <div class="card-body">
        <h2 class="card-title truncate">Books title</h2>
        <div class="card-actions">
            <MainButton label="See more" />
        </div>
    </div>
</div>
