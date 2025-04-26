<script>
    import { page } from '$app/stores';

    let currentPath = '';
    $: currentPath = $page.url.pathname;

    const discordLink = 'https://discord.gg/your-discord-link'; // Replace with link
    const serverIP = 'play.pixeltown.com';                      // Replace with IP

    function copyToClipboard() {
        if (typeof navigator !== 'undefined' && navigator.clipboard) {
            navigator.clipboard.writeText(serverIP).then(() => {
                alert('Server IP copied to clipboard!');
            }).catch(err => {
                console.error('Failed to copy text: ', err);
            });
        }
    }
</script>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css">

<header>
    <div class="container top-bar">
        <div>
            <a href={discordLink} target="_blank" rel="noopener noreferrer" class="hovered">
                <i class="fab fa-discord"></i> Join The Discord
            </a>
        </div>
        <div>
            <a href="#" on:click|preventDefault={copyToClipboard} class="hovered">
                <i class="fas fa-copy"></i> Copy Server IP
            </a>
        </div>
    </div>
</header>

<nav>
    <div class="container nav-container">
        <div class="nav-links-left">
            <a href="/" class={currentPath === '/' ? 'active' : ''}>Home</a>
            <a href="/Join" class={currentPath === '/Join' ? 'active' : ''}>Join</a>
        </div>
        <a href="/" class="logo-pokeball">
            <img src="https://pngimg.com/uploads/pokeball/pokeball_PNG6.png" alt="Pokeball" style="object-fit: cover; width: 101%" />
        </a>
        <div class="nav-links-right">
            <a href="/Vote" class={currentPath === '/Vote' ? 'active' : ''}>Vote</a>
            <a href="/Store" class={currentPath === '/Store' ? 'active' : ''}>Store</a>
        </div>
    </div>
</nav>

<style>
    nav a.active {
        color: #333;
    }
    .active::after {
        width: 100%;
        left: 0;
        background: #F4A261;
    }

    .logo-pokeball {
        margin: 0;
        padding: 0;
        transition: border-color 0.5s ease, filter 0.3s ease; /* Smooth animation for border and filter */
        border-color: white;
    }

    .logo-pokeball::after{
        display:none;
    }

    .logo-pokeball img {
        transition: filter 0.3s ease; /* Smooth transition for grayscale effect */
    }

    .logo-pokeball:hover {
        border-color: #F4A261; /* Change border color to orange */
    }

    .logo-pokeball:hover img {
        filter: brightness(0.8); /* Slightly darken the image */
    }

    .hovered {
        transition: color 0.3s ease
    }

    .hovered:hover {
        color: #67e6eb;
        font-weight: 600;
    }
</style>