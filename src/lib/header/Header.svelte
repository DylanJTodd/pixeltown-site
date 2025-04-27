<script>
    import { page } from '$app/stores';

    let currentPath = '';
    $: currentPath = $page.url.pathname;

    const discordLink = 'https://discord.gg/your-discord-link'; // Replace with your actual Discord link
    const serverIP = 'play.pixeltown.com';                      // Replace with your actual server IP

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
    <div class="top-bar">
        <div>
            <a href={discordLink} target="_blank" rel="noopener noreferrer" class="hovered">
                <i class="fab fa-discord"></i> Join The Discord
            </a>
        </div>
        <div class="right-aligned">
            <a href="#" on:click|preventDefault={copyToClipboard} class="hovered">
            <i class="fas fa-copy"></i> Copy Server IP
            </a>
        </div>
    </div>
</header>

<nav>
    <div class="nav-container">
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
        transition: border-color 0.5s ease, filter 0.3s ease;
        border-color: white;
    }

    .logo-pokeball::after{
        display:none;
    }

    .logo-pokeball img {
        transition: filter 0.3s ease;
    }

    .logo-pokeball:hover {
        border-color: #F4A261;
    }

    .logo-pokeball:hover img {
        filter: brightness(0.8);
    }

    .hovered {
        transition: color 0.3s ease
    }

    .hovered:hover {
        color: #67e6eb;
        font-weight: 600;
    }

    .right-aligned {
        margin-left: auto;
        text-align: right !important;
    }

    .nav-container {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: nowrap;
        gap: 5px;
    }

    .nav-links-left,
    .nav-links-right {
        display: flex;
        align-items: center;
        flex-wrap: nowrap;
        justify-content: flex-end;
        gap: 5px;
    }

    @media (max-width: 768px) {
        .nav-container {
            justify-content: center;
            gap: 10px;
        }

        .nav-links-left,
        .nav-links-right {
            justify-content: center; /* Ensure links stay centered */
        }
    }
</style>