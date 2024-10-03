<script>import "../app.css";</script>
<svelte:head>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
<link href="https://fonts.googleapis.com/css2?family=Inria+Sans:ital,wght@0,300;0,400;0,700;1,300;1,400;1,700&amp;family=Manrope:wght@200..800&amp;display=swap" rel="stylesheet" />
</svelte:head>
<slot></slot>


<nav class="bg-gray-800 p-4 fixed w-full top-0 z-50">
    <div class="container mx-auto flex justify-between items-center">
        <!-- Left side: Welcome Text -->
        <div class="text-white font-bold text-lg">
            Welcome to my portfolio
        </div>

        <!-- Right side: Nav Links -->
        <div class="space-x-4">
            <a href="/" class="text-white hover:bg-gray-700 focus:ring-4 focus:ring-gray-500 font-semibold rounded-lg px-4 py-2 transition duration-200">Home</a>
            <a href="/about" class="text-white hover:bg-gray-700 focus:ring-4 focus:ring-gray-500 font-semibold rounded-lg px-4 py-2 transition duration-200">About</a>
            <a href="/portfolio" class="text-white hover:bg-gray-700 focus:ring-4 focus:ring-gray-500 font-semibold rounded-lg px-4 py-2 transition duration-200">Portfolio</a>
            <a href="/contact" class="text-white hover:bg-gray-700 focus:ring-4 focus:ring-gray-500 font-semibold rounded-lg px-4 py-2 transition duration-200">Contact Me</a>
        </div>
    </div>
</nav>

<!-- Ensure page content is pushed down to accommodate the fixed nav -->
<!-- <div class="pt-16">
    <slot></slot>
</div> -->
  
  
  