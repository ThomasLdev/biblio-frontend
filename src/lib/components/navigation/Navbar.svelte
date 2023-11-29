<script>
    export let duration = "300ms";
    export let offset = 0;
    export let tolerance = 0;

    let headerClass = "translate-y-0";
    let y = 0;
    let lastY = 0;

    function deriveClass(y, dy) {
        if (y < offset) {
            return "translate-y-0";
        }

        if (Math.abs(dy) <= tolerance) {
            return headerClass;
        }

        if (dy < 0) {
            return "-translate-y-[90px]";
        }

        return "translate-y-0";
    }

    function updateClass(y) {
        const dy = lastY - y;
        lastY = y;
        return deriveClass(y, dy);
    }

    function setTransitionDuration(node) {
        node.style.transitionDuration = duration;
    }

    $: headerClass = updateClass(y);
</script>

<nav use:setTransitionDuration class="navbar bg-neutral text-neutral-content z-10 fixed top-0 {headerClass}">
    <div class="flex-1">

        <a href="/" class="btn btn-ghost text-xl">Biblio</a>
    </div>
    <div class="flex-none gap-2">
        <div class="dropdown dropdown-end">
            <div tabindex="0" role="button" class="btn btn-ghost btn-circle avatar">
                <div class="w-10 rounded-full">
                    <img alt="Tailwind CSS Navbar component"
                         src="https://daisyui.com/images/stock/photo-1534528741775-53994a69daeb.jpg"/>
                </div>
            </div>
            <ul class="mt-3 z-[1] p-2 shadow menu menu-sm dropdown-content bg-base-100 rounded-box w-52">
                <li>
                    <a class="justify-between">
                        Profile
                        <span class="badge">New</span>
                    </a>
                </li>
                <li><a>Settings</a></li>
                <li><a>Logout</a></li>
            </ul>
        </div>
    </div>
</nav>

<svelte:window bind:scrollY={y}/>
