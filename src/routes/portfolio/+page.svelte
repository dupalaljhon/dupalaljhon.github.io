<style>
    /* Container styles */
    .flex-container {
      background-color: #3f3f46;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
    }
  
    /* Text and heading styles */
    .work-heading {
      margin-top: 0px;
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
      width: 100px;
      ring: 4px solid white;
      object-fit: cover;
      transition: transform 0.3s ease;
    }
  
    .image-container img:hover {
      transform: scale(1.05); /* Enlarge image slightly on hover */
    }
  
    /* Larger screen adjustments */
    @media (min-width: 1024px) {
      .work-heading {
        font-size: 2rem;
        margin-bottom: 40px;
      }
  
      .image-container img {
        height: 240px;
        width: 240px;
      }
    }
  
    /* Tablet adjustments */
    @media (max-width: 768px) {
      .work-heading {
        font-size: 1.7rem;
      }
  
      .image-container img {
        height: 150px;
        width: 150px;
      }
    }
  
    /* Mobile adjustments */
    @media (max-width: 480px) {
      .work-heading {
        font-size: 1.2rem;
      }
  
      .image-container img {
        height: 90px;
        width: 90px;
      }
    }
  </style>
  
  <div class="flex-container">
    <div class="flex flex-col items-center">
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
    </div>
  </div>
  