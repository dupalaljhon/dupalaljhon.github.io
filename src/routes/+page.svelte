<script>
  import { onMount } from 'svelte';
  let isTypingFinished = false;

  onMount(() => {
    const typingText = document.getElementById('typingText');
    
    // @ts-ignore
    typingText.addEventListener('animationend', () => {
      isTypingFinished = true;
    });
  });
</script>

<style>
  .typing {
    overflow: hidden;
    border-right: 2px solid white;
    white-space: nowrap;
    animation: typing 2.5s steps(20, end) forwards, blink-caret 0.50s step-end infinite;
  }

  @keyframes typing {
    from { width: 0; }
    to { width: 100%; }
  }

  @keyframes blink-caret {
    from, to { border-color: transparent; }
    50% { border-color: white; }
  }

  .typing-finished {
    animation: none;
    border-right: none; 
  }
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    max-width: 100%;
    padding: 20px;
    margin-top: 20px;
  }

  @media (min-width: 1024px) {
    .container {
      flex-direction: row;
    }
  }

  .text-container {
    flex: 1;
    padding-left: 20px;
    margin-top: 50px;
    text-align: center;
  }

  @media (min-width: 1024px) {
    .text-container {
      text-align: left;
      padding-left: 80px;
      margin-top: 150px;
    }
  }

  .image-container {
    flex-shrink: 0;
    margin-top: 50px;
    padding-right: 20px;
  }

  @media (min-width: 1024px) {
    .image-container {
      margin-top: 175px;
      padding-right: 100px;
    }
  }

  img {
    box-shadow: 0 0 30px rgba(0, 123, 255, 0.7), 0 0 60px rgba(100, 100, 255, 0.5), 0 0 100px rgba(200, 50, 255, 0.3), 0 0 10px 10px rgba(255, 255, 255, 0.8);
    width: 100%;
    max-width: 200px;
  }

  @media (min-width: 1024px) {
    img {
      max-width: 400px;
    }
  }
</style>

<div style="background-color: #585858; min-height: 100vh; padding: 20px;">
  <div class="container">
    <div class="text-container">
      <h3 class="text-2xl lg:text-4xl font-bold text-white mb-2 lg:mb-4">Hello, It's me</h3>
      <h1 class="text-4xl lg:text-6xl font-bold text-white mb-2 lg:mb-4">AL JHON DUPAL</h1>

      <div class="overflow-hidden">
        <h3 id="typingText" class="text-xl lg:text-3xl font-bold text-white mb-2 lg:mb-4 typing {isTypingFinished ? 'typing-finished' : ''}">
          And I am an Information Technology Student.
        </h3>
      </div>
    </div>
    
    <div class="image-container">
      <div class="relative rounded-full h-40 w-40 lg:h-80 lg:w-80">
        <div class="absolute inset-0 bg-gradient-to-r from-blue-600 via-sky-600 to-red-900 rounded-full opacity-50 animate-pulse"></div>

        <img src="/myphoto.jpg" alt="AL JHON DUPAL" class="relative rounded-full h-40 w-40 lg:h-80 lg:w-80 shadow-lg ring-4 ring-white">
      </div>
    </div>
  </div>
</div>
