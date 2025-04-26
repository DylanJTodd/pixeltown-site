<script>
    import { onMount } from "svelte";

    let selected = ""; // No default selection

    onMount(() => {
        // Get the current path from the browser's location
        const currentPath = window.location.pathname;

        // Match the path to the corresponding navigation item
        switch (currentPath) {
            case "/":
                selected = "Home";
                break;
            case "/Join":
                selected = "Join";
                break;
            case "/Vote":
                selected = "Vote";
                break;
            case "/Store":
                selected = "Store";
                break;
            default:
                selected = ""; // No match
        }
    });

    function selectItem(item) {
        selected = item;
    }
</script>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<div style="position: relative; width: 100%;">
    <!-- Banner Image -->
    <img src="/banner.png" alt="Pixeltown banner" class="banner-image" style="width: 100%;">

    <!-- Navigation buttons -->
    <nav style="position: absolute; bottom: -10%; left: 49.6%; transform: translateX(-50%); display: flex; align-items: center;">
        <ul class="nav" style="list-style: none; display: flex; align-items: center; padding: 0; margin: 0; gap: 2rem;">
            <li>
                <a 
                    href="/" 
                    class:selected={selected === "Home"} 
                    on:click={() => selectItem("Home")} 
                    style="text-decoration: none;"
                >Home</a>
            </li>
            <li>
                <a 
                    href="/Join" 
                    class:selected={selected === "Join"} 
                    on:click={() => selectItem("Join")} 
                    style="text-decoration: none;"
                >Join</a>
            </li>
        </ul>
        <div id="logo-gap" style="flex-shrink: 0;"></div>
        <ul class="nav" style="list-style: none; display: flex; align-items: center; padding: 0; margin: 0; gap: 2rem;">
            <li>
                <a 
                    href="/Vote" 
                    class:selected={selected === "Vote"} 
                    on:click={() => selectItem("Vote")} 
                    style="text-decoration: none;"
                >Vote</a>
            </li>
            <li>
                <a 
                    href="/Store" 
                    class:selected={selected === "Store"} 
                    on:click={() => selectItem("Store")} 
                    style="text-decoration: none;"
                >Store</a>
            </li>
        </ul>
    </nav>
    
    <!-- Logo Image -->
    <a href="/" style="position: absolute; top: 40%; left: 50%; transform: translateX(-50%);">
        <img src="/logo.png" alt="Pixeltown logo" id="logo">
    </a>

    <!-- Discord and IP Banner Links-->
    <a class="banner-links" href="/" style="left: 1%; display: flex; flex-direction: column; align-items: flex-start; gap: 0.5rem;"> 
        <div style="display: flex; align-items: center; gap: 0.5rem; line-height: 0.1;">
            <i class="fa-solid fa-copy"></i>
            <p style="margin: 0;">Join The Discord</p>
        </div>
        <p style="margin: 0; font-size: 80%; font-weight: 400; line-height: 0.1;">Click to copy</p>
    </a>

    <a class="banner-links" href="/" style="right: 1%; display: flex; flex-direction: column; align-items: flex-start; gap: 0.5rem;"> 
        <div style="display: flex; align-items: center; gap: 0.5rem; line-height: 0.1;">
            <i class="fa-solid fa-copy"></i>
            <p style="margin: 0;">Copy Server IP</p>
        </div>
        <p style="margin: 0; font-size: 80%; font-weight: 400; line-height: 0.1;">Click to copy</p>
    </a>
</div>

<style>
a.selected {
    font-size: 110%;
    text-decoration: underline !important;
    font-weight: 800;
    color: #ff0000;
}
</style>