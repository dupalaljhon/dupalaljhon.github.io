<style>
    /* Container styles */
    .flex-container {
      background-color: #3f3f46;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      padding: 20px;
    }

    /* Text and heading styles */
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

    /* Image row and image styling */
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
      position: relative; /* For absolute positioning of the arrow */
    }

    .image-container img {
      height: 100px;
      width: 110px;
      border: 4px solid #fff;
      border-radius: 10px;
      object-fit: cover;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      cursor: pointer; /* Indicate that the image is clickable */
    }

    .image-container img:hover {
      transform: scale(1.1);
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
    }

    /* Video file name styling */
    .video-file-name {
      color: #f1f1f1;
      font-weight: bold;
      text-align: center;
      font-size: 1.8rem;
      margin-bottom: 10px;
    }

    /* Subheading styling */
    .sub-heading {
      color: #ccc;
      font-weight: normal;
      font-size: 1.2rem;
      margin-top: -10px;
      margin-bottom: 20px;
    }

    /* Video player styling */
    .video-player {
      margin-top: 20px;
      margin-bottom: 20px;
      width: 100%;
      max-width: 1000px; /* Adjust as needed */
      border-radius: 10px;
      border: 4px solid #fff;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.4);
    }

    /* Arrow styling */
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

    /* Larger screen adjustments */
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

    /* Tablet adjustments */
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

    /* Mobile adjustments */
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

    /* Modal styles */
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
        z-index: 1000; /* Ensure modal is on top */
    }
</style>

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

    const openImage = (index) => {
        currentIndex = index;
        isZoomed = true;
    };

    const nextImage = () => {
        if (currentIndex < images.length - 1) {
            currentIndex++;
        } else {
            currentIndex = 0; // loop back to the first image
        }
    };

    const closeZoom = () => {
        isZoomed = false;
    };
</script>

<div class="flex-container">
    <h1 class="work-heading">My Digital Design and Multimedia System Works</h1>
    
    <!-- Top Row with 5 Images -->
    <div class="image-row">
        {#each images as image, index}
            <div class="image-container" on:click={() => openImage(index)}>
                <img src={image} alt="AL JHON DUPAL" />
            </div>
        {/each}
    </div>

    <!-- Zoomed Image Modal -->
    {#if isZoomed}
        <div class="modal" on:click={closeZoom}>
            <img src={images[currentIndex]} alt="Zoomed Image" style="width: 80%; max-width: 800px;"/>
            <button class="arrow arrow-left" on:click|stopPropagation={nextImage}>❮</button>
            <button class="arrow arrow-right" on:click|stopPropagation={nextImage}>❯</button>
        </div>
    {/if}

    <!-- Video File Name -->
    <div class="video-file-name">
        <h1>My AppDev Assessment</h1>
        <p class="sub-heading">Image Gallery</p>
    </div>

    <!-- Video Player -->
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
</div>
