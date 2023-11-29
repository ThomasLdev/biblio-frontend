<script>
    import "../app.css";

    import Navbar from '$navigation/Navbar.svelte'
    import Footer from '$navigation/Footer.svelte'
</script>

<Navbar />

<slot></slot>

<Footer />
