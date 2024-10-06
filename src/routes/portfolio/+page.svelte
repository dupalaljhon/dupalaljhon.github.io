<script>
    import { onMount } from "svelte";

    let images = [
        "/mywork1.png",
        "/mywork2.png",
        "/mywork3.png",
        "/mywork4.png",
        "/mywork5.png"
    ];
    
    let currentIndex = 0;
    let isZoomed = false;

    const openImage = (/** @type {number} */ index) => {
        currentIndex = index;
        isZoomed = true;
    };

    const nextImage = () => {
        currentIndex = (currentIndex < images.length - 1) ? currentIndex + 1 : 0; // loop back to the first image
    };

    const closeZoom = () => {
        isZoomed = false;
    };
</script>

<style>
    .flex-container {
        background-color: #585858;
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        padding: 20px;
    }

    .work-heading {
        margin-top: 100px;
        text-align: center;
        font-weight: bold;
        color: #f1f1f1;
        margin-bottom: 20px;
        font-size: 2rem;
        text-transform: uppercase;
        letter-spacing: 1.5px;
    }

    .logo-heading {
        margin-top: 5px;
        text-align: center;
        font-weight: bold;
        color: #f1f1f1;
        margin-bottom: 10px;
        font-size: 2rem;
        text-transform: uppercase;
        letter-spacing: 1.5px;
    }

    .image-row {
        display: flex;
        justify-content: center;
        gap: 20px;
        margin-bottom: 40px;
        flex-wrap: wrap;
    }

    .image-container {
        flex-shrink: 0;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
        position: relative; 
        cursor: pointer;
    }

    .image-container img {
        height: 100px;
        width: 110px;
        border: 4px solid #fff;
        border-radius: 10px;
        object-fit: cover;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .image-container img:hover {
        transform: scale(1.1);
        box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
    }

    .video-file-name {
        color: #f1f1f1;
        font-weight: bold;
        text-align: center;
        font-size: 1.8rem;
        margin-bottom: 10px;
    }

    .sub-heading {
        color: #f1f1f1;
        font-weight: bold;
        text-align: center;
        font-size: 1.8rem;
        margin-top: -10px;
        margin-bottom: 20px;
    }

    .video-player {
        margin-top: 20px;
        margin-bottom: 20px;
        width: 100%;
        max-width: 1000px; 
        border-radius: 10px;
        border: 4px solid #fff;
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.4);
    }

    .arrow {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        background-color: rgba(0, 0, 0, 0.7);
        color: white;
        border: none;
        border-radius: 5px;
        padding: 10px;
        cursor: pointer;
        z-index: 1;
    }

    .arrow-left {
        left: 10px;
    }

    .arrow-right {
        right: 10px;
    }

    @media (min-width: 1024px) {
        .work-heading {
            font-size: 2.5rem;
            margin-bottom: 40px;
        }

        .image-container img {
            height: 240px;
            width: 250px;
        }

        .video-file-name {
            font-size: 2rem;
        }
    }

    @media (max-width: 768px) {
        .work-heading {
            font-size: 2rem;
        }

        .image-container img {
            height: 150px;
            width: 160px;
        }

        .video-file-name {
            font-size: 1.7rem;
        }
    }

    @media (max-width: 480px) {
        .work-heading {
            font-size: 1.5rem;
        }

        .image-container img {
            height: 90px;
            width: 100px;
        }

        .video-file-name {
            font-size: 1.3rem;
        }
    }

    .modal {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: rgba(0, 0, 0, 0.8);
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 1000; 
    }

    .logo-container {
    display: flex;
    justify-content: center;
    gap: 25px; 
    margin-top: 20px;
    margin-bottom: 100px;
    flex-wrap: wrap; /* Allow logos to wrap on smaller screens */
}

.logo-container img {
    width: 10%; /* Adjust the width as needed */
    max-width: 100px; /* Max width for larger screens */
    height: auto; /* Maintain aspect ratio */
    transition: transform 0.3s ease; /* Add a hover effect */
}

.logo-container img:hover {
    transform: scale(1.1); /* Scale up the logo on hover */
}

</style>

<div class="flex-container">
    <h1 class="work-heading">My Digital Design and Multimedia System Works</h1>
    
    <div class="image-row">
        {#each images as image, index}
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <div class="image-container" on:click={() => openImage(index)} role="button" tabindex="0">
                <img src={image} alt="AL JHON DUPAL" />
            </div>
        {/each}
    </div>

    {#if isZoomed}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <!-- svelte-ignore a11y-no-static-element-interactions -->
        <div class="modal" on:click={closeZoom}>
            <!-- svelte-ignore a11y-img-redundant-alt -->
            <img src={images[currentIndex]} alt="Zoomed Image" style="width: 80%; max-width: 800px;"/>
            <button class="arrow arrow-left" on:click|stopPropagation={nextImage}>❮</button>
            <button class="arrow arrow-right" on:click|stopPropagation={nextImage}>❯</button>
        </div>
    {/if}

    <div class="video-file-name">
        <h1>My AppDev Assessment</h1>
        <p class="sub-heading">Image Gallery</p>
    </div>
    
    <video class="video-player" controls>
        <source src="/mywork6.mp4" type="video/mp4">
        <track src="/mywork6.mp4" kind="captions" srclang="en" label="English captions">
    </video>
    
    <div class="video-file-name" style="margin-top: 50px">
        <h1>Pong Game using Java</h1>
    </div>

    <video class="video-player" controls>
        <source src="/mywork7.mp4" type="video/mp4">
        <track src="/mywork7.mp4" kind="captions" srclang="en" label="English captions">
    </video>
    <h1 class="logo-heading">My Skills</h1>
    <div class="logo-container">
        
        <img
            width="100"
            alt="Angular Logo"
            src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNTAgMjUwIj4KICAgIDxwYXRoIGZpbGw9IiNERDAwMzEiIGQ9Ik0xMjUgMzBMMzEuOSA2My4ybDE0LjIgMTIzLjFMMTI1IDIzMGw3OC45LTQzLjcgMTQuMi0xMjMuMXoiIC8+CiAgICA8cGF0aCBmaWxsPSIjQzMwMDJGIiBkPSJNMTI1IDMwdjIyLjItLjFWMjMwbDc4LjktNDMuNyAxNC4yLTEyMy4xTDEyNSAzMHoiIC8+CiAgICA8cGF0aCAgZmlsbD0iI0ZGRkZGRiIgZD0iTTEyNSA1Mi4xTDY2LjggMTgyLjZoMjEuN2wxMS43LTI5LjJoNDkuNGwxMS43IDI5LjJIMTgzTDEyNSA1Mi4xem0xNyA4My4zaC0zNGwxNy00MC45IDE3IDQwLjl6IiAvPgogIDwvc3ZnPg=="
        />


        <img
            width="100"
            alt="Java Logo"
            src="https://www.vectorlogo.zone/logos/java/java-horizontal.svg"
        />

        <img
            width="100"
            alt="HTML Logo"
            src="https://www.vectorlogo.zone/logos/w3_html5/w3_html5-icon.svg"
        />

        <img
            width="100"
            alt="CSS Logo"
            src="https://www.vectorlogo.zone/logos/w3_css/w3_css-official.svg"
        />

        <img
            width="100"
            alt="PHP Logo"
            src="https://www.vectorlogo.zone/logos/php/php-horizontal.svg"
        />
        <img
        width="100"
        alt="Photoshop Logo"
        src="/icons8-photoshop-94.png"
    />

    <img
    width="100"
    alt="Svelte Logo"
    src="https://www.vectorlogo.zone/logos/sveltetechnology/sveltetechnology-icon.svg"
/>
        
    </div>
</div>
