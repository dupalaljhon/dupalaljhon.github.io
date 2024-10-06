<script>
  import { Button } from 'flowbite-svelte'; 
  import { ArrowUpOutline, ArrowDownOutline } from 'flowbite-svelte-icons'; 
  let showMore = false;
</script>

<div style="background-color: #3f3f46; min-height: 100vh;" class="flex items-center justify-center">
  <div class="rounded-lg shadow-lg p-6 sm:p-8 md:p-10 max-w-4xl sm:max-w-5xl text-center mx-auto" style="margin-top: 100px; background-color: #404045;">
    <h3 class="text-xl sm:text-2xl md:text-3xl font-bold text-white mb-4">About me</h3>
    
    <p class="text-sm sm:text-base md:text-lg text-white mb-4">
      Hello! Al Jhon Dupal, a 23-year-old I am a BS Information Technology student at Gordon College. My dream before was to be BS Marine Transportation. Before entering college, due to not enough income from my parents, I decided to choose another course that didn’t need spending money and has high-paying job prospects in the future. Since my family couldn't afford the costs for that course, I chose a more reasonable pathway, a BS in Information Technology (BSIT). I chose this field since it provides lots of career options and could potentially lead to well-paying positions. 
      <br><br>
      In 2020, I started as a regular student with dreams to achieve. However, when the pandemic hit, everything changed. I had already enrolled in the BSIT program at Gordon College, and all our classes shifted online. During my first year, I learned valuable lessons that opened my eyes to what the future holds in the IT field. I successfully completed my first year in 2021, but then faced a significant challenge: my computer, which I used for attending classes and completing assignments, broke down. Unfortunately, we couldn’t afford a replacement.
    </p>

    {#if showMore}
      <p class="text-sm sm:text-base md:text-lg text-white mb-4">
        I finished my first year in 2021; unfortunately, my computer that I used to join classes and do the activities was damaged, and we didn't have money for a replacement. Due to my family's financial problems and the economy reopening, the prices of goods were really high, and we could not afford to buy some stocks for our house. Then, I decided to stop my studies and get a job to help them. I used to be a factory worker as my job, and I saved a little bit of money to have savings to continue my studies.
      </p>
  
      <p class="text-sm sm:text-base md:text-lg text-white mb-4">
        After two years of working and saving, I finally had enough money to return to my studies. Thankfully, my family’s financial situation had improved a little, and we were no longer struggling as much. I decided to pursue my education again because I’m determined to earn a diploma—something no one in my family has achieved yet.
      </p>
  
      <p class="text-sm sm:text-base md:text-lg text-white mb-4">
        On the first day back in class, I felt a bit nervous and shy due to the two-year age gap between me and my classmates, but over time, I was able to adjust and fit in. Although I’m not particularly skilled in programming, I excel in technical areas like hardware. Still, I’m pushing myself to learn and improve as a developer because I know that programming skills can lead to high-paying job opportunities in the future.
      </p>
    {/if}

    <div class="mt-6 flex justify-center">
      <Button color="dark" on:click={() => showMore = !showMore} class="flex items-center gap-2">
        {#if showMore}
          <ArrowUpOutline class="w-6 h-6 text-white" />
          <span>Read Less</span>
        {:else}
          <ArrowDownOutline class="w-6 h-6 text-white" />
          <span>Read More</span>
        {/if}
      </Button>
    </div>
  </div>
</div>
