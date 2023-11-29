<script>
    import Container from '$layout/Container.svelte'
</script>

<main class="bg-gray-900">
    <Container>
        <div class="hero">
            <div class="hero-content text-center">
                <div class="max-w-md">
                    <h1 class="text-5xl font-bold">Welcome to Biblio</h1>
                    <p class="py-6">With Biblio, you'll never lose a book again.</p>
                </div>
            </div>
        </div>

        <form action="" class="flex gap-2 justify-between mb-4">
            <label for="search-book" class="w-full">
                <input class="input input-bordered md:w-auto w-full"
                       id="search-book"
                       name="search-book"
                       type="text"
                       placeholder="Search by title, author, isbn, etc...">
            </label>
            <button type="submit" class="btn btn-primary">Go !</button>
        </form>

        <a class="underline pt-5"
           href="/books">
            or manage your book collection
        </a>
    </Container>
</main>

