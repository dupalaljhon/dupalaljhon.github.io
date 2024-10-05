<style>
    /* Container styles */
    .flex-container {
      background-color: #3f3f46;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
    }

    /* Text and heading styles */
    .work-heading {
      margin-top: 100px;
      text-align: center;
      font-weight: bold;
      color: white;
      margin-bottom: 20px;
      font-size: 1.5rem;
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
    }

    .image-container img {
      height: 100px;
      width: 110px;
      ring: 4px solid white;
      object-fit: cover;
      transition: transform 0.3s ease;
    }

    .image-container img:hover {
      transform: scale(1.05);
    }

    /* Video file name styling */
    .video-file-name {
      color: white;
      font-weight: bold;
      text-align: center;
      font-size: 1.5rem;
    }

    /* Video player styling */
    .video-player {
      margin-top: 20px;
      margin-bottom: 20px;
      width: 100%;
      max-width: 1000px; /* Adjust as needed */
    }

    /* Larger screen adjustments */
    @media (min-width: 1024px) {
      .work-heading {
        font-size: 2rem;
        margin-bottom: 40px;
      }

      .image-container img {
        height: 240px;
        width: 250px;
      }

      .video-file-name {
        font-size: 1.5rem;
      }
    }

    /* Tablet adjustments */
    @media (max-width: 768px) {
      .work-heading {
        font-size: 1.7rem;
      }

      .image-container img {
        height: 150px;
        width: 160px;
      }

      .video-file-name {
        font-size: 1.3rem;
      }
    }

    /* Mobile adjustments */
    @media (max-width: 480px) {
      .work-heading {
        font-size: 1.2rem;
      }

      .image-container img {
        height: 90px;
        width: 100px;
      }

      .video-file-name {
        font-size: 1rem;
      }
    }
</style>

<div class="flex-container">
    <h1 class="work-heading">My Digital Design and Multimedia System Works</h1>
    
    <!-- Top Row with 5 Images -->
    <div class="image-row">
        <div class="image-container">
            <img src="/mywork1.png" alt="AL JHON DUPAL">
        </div>
        <div class="image-container">
            <img src="/mywork2.png" alt="AL JHON DUPAL">
        </div>
        <div class="image-container">
            <img src="/mywork3.png" alt="AL JHON DUPAL">
        </div>
        <div class="image-container">
            <img src="/mywork4.png" alt="AL JHON DUPAL">
        </div>
        <div class="image-container">
            <img src="/mywork5.png" alt="AL JHON DUPAL">
        </div>
    </div>

    <!-- Video File Name -->
    <div class="video-file-name">
        <h1 class="video-file-name">My AppDev Assessment</h1>
        <p class="video-file-name">Image Gallery</p>
    </div>

    <!-- Video Player -->
    <video class="video-player" controls>
        <source src="/mywork6.mp4" type="video/mp4">
        <track src="/captions/mywork6.mp4" kind="captions" srclang="en" label="English captions">
    
    </video>
    
    
</div>
