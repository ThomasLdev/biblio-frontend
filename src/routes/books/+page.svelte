<script>
    import Container from '$layout/Container.svelte'
    import Card from "$ui/Card.svelte"
    import Pagination from "$navigation/Pagination.svelte"

    import data from "../../bookData";
</script>

<Container>
    <h1 class="text-5xl font-bold pb-5 text-center">
        Manage your awesome book collection
    </h1>

    <div class="form-control mb-5">
        <input type="text"
               placeholder="Search your collection..."
               class="input input-bordered md:w-auto text-center"
        />
    </div>

    <div class="grid grid-cols-1 lg:grid-cols-2 gap-4">
        { #each data["hydra:member"] as item }
            <Card data={ item } />
        { /each }
    </div>

    <Pagination links={data["hydra:view"]} />
</Container>
