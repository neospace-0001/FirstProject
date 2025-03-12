<template>
  <section class="w-full bg-orange py-2 md:py-4 text-white">
    <div
      class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex justify-between items-center"
    >
      <!-- Left: Contact Information -->
      <ul
        class="flex justify-center items-center text-xs sm:text-sm gap-2 sm:gap-4"
      >
        <!-- Opening Hours -->
        <li class="flex items-center gap-1">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-4 h-4"
            aria-hidden="true"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M12 6v6h4.5m4.5 0a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z"
            />
          </svg>
          <span>9:00am - 6:00pm Mon-Fri</span>
        </li>
        <li class="border border-white pt-3"></li>

        <!-- Phone Number -->
        <li class="flex items-center gap-1">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-4 h-4"
            aria-hidden="true"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 0 0 2.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 0 1-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 0 0-1.091-.852H4.5A2.25 2.25 0 0 0 2.25 4.5v2.25Z"
            />
          </svg>
          <a href="tel:+254745893963" class="hover:underline">+254745893963</a>
        </li>
        <li class="border border-white pt-3"></li>

        <!-- Location -->
        <li class="flex items-center gap-1">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-4 h-4"
            aria-hidden="true"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M15 10.5a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z"
            />
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1 1 15 0Z"
            />
          </svg>
          <span>Nakuru, Kenya</span>
        </li>
      </ul>

      <!-- Right: Social Media Icons (Placeholder) -->
      <div class="flex items-center gap-5">
        <a href="#" aria-label="Facebook" class="hover:text-gray-200">
          <i class="fab fa-facebook-f fa-sm" aria-hidden="true"></i>
        </a>
        <a href="#" aria-label="X (Twitter)" class="hover:text-gray-200">
          <i class="fab fa-x-twitter fa-sm" aria-hidden="true"></i>
        </a>
        <a href="#" aria-label="Instagram" class="hover:text-gray-200">
          <i class="fab fa-instagram fa-sm" aria-hidden="true"></i>
        </a>
        <a href="#" aria-label="LinkedIn" class="hover:text-gray-200">
          <i class="fab fa-linkedin-in fa-sm" aria-hidden="true"></i>
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>

</script>
