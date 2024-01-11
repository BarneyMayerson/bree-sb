<script setup>
import { Head, Link } from "@inertiajs/vue3";
import ThemeDropdown from "@/Components/ThemeDropdown.vue";

defineProps({
  canLogin: Boolean,
  canRegister: Boolean,
  laravelVersion: String,
  phpVersion: String,
});
</script>

<template>
  <Head title="Welcome" />

  <div
    class="relative sm:flex sm:justify-center sm:items-center min-h-screen bg-dots-darker bg-center bg-gray-100 dark:bg-dots-lighter dark:bg-gray-900 selection:bg-red-500 selection:text-white"
  >
    <div v-if="canLogin" class="sm:fixed sm:top-0 sm:end-0 p-6 text-end z-10">
      <Link
        v-if="$page.props.auth.user"
        :href="route('dashboard')"
        class="font-semibold text-gray-600 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
        >Dashboard</Link
      >

      <template v-else>
        <Link
          :href="route('login')"
          class="font-semibold text-gray-600 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
          >Log in</Link
        >

        <Link
          v-if="canRegister"
          :href="route('register')"
          class="ms-4 font-semibold text-gray-600 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
          >Register</Link
        >
      </template>
    </div>

    <div class="max-w-7xl mx-auto p-6 lg:p-8">
      <div class="text-gray-900 dark:text-gray-400">
        <ThemeDropdown />
      </div>

      <div class="mt-16">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 lg:gap-8">
          <a
            href="https://laravel.com/docs"
            class="scale-100 p-6 bg-white dark:bg-gray-800/50 dark:bg-gradient-to-bl from-gray-700/50 via-transparent dark:ring-1 dark:ring-inset dark:ring-white/5 rounded-lg shadow-2xl shadow-gray-500/20 dark:shadow-none flex motion-safe:hover:scale-[1.01] transition-all duration-250 focus:outline focus:outline-2 focus:outline-red-500"
          >
            <div>
              <h2
                class="mt-6 text-2xl font-semibold text-gray-900 dark:text-white"
              >
                Documentation
              </h2>

              <p class="mt-4 text-gray-500 dark:text-gray-400 leading-relaxed">
                Laravel has wonderful documentation covering every aspect of the
                framework. Whether you are a newcomer or have prior experience
                with Laravel, we recommend reading our documentation from
                beginning to end.
              </p>
            </div>
          </a>

          <a
            href="https://laracasts.com"
            class="scale-100 p-6 bg-white dark:bg-gray-800/50 dark:bg-gradient-to-bl from-gray-700/50 via-transparent dark:ring-1 dark:ring-inset dark:ring-white/5 rounded-lg shadow-2xl shadow-gray-500/20 dark:shadow-none flex motion-safe:hover:scale-[1.01] transition-all duration-250 focus:outline focus:outline-2 focus:outline-red-500"
          >
            <div>
              <h2
                class="mt-6 text-2xl font-semibold text-gray-900 dark:text-white"
              >
                Laracasts
              </h2>

              <p class="mt-4 text-gray-500 dark:text-gray-400 leading-relaxed">
                Laracasts offers thousands of video tutorials on Laravel, PHP,
                and JavaScript development. Check them out, see for yourself,
                and massively level up your development skills in the process.
              </p>
            </div>
          </a>

          <a
            href="https://laravel-news.com"
            class="scale-100 p-6 bg-white dark:bg-gray-800/50 dark:bg-gradient-to-bl from-gray-700/50 via-transparent dark:ring-1 dark:ring-inset dark:ring-white/5 rounded-lg shadow-2xl shadow-gray-500/20 dark:shadow-none flex motion-safe:hover:scale-[1.01] transition-all duration-250 focus:outline focus:outline-2 focus:outline-red-500"
          >
            <div>
              <h2
                class="mt-6 text-2xl font-semibold text-gray-900 dark:text-white"
              >
                Laravel News
              </h2>

              <p class="mt-4 text-gray-500 dark:text-gray-400 leading-relaxed">
                Laravel News is a community driven portal and newsletter
                aggregating all of the latest and most important news in the
                Laravel ecosystem, including new package releases and tutorials.
              </p>
            </div>
          </a>

          <div
            class="scale-100 p-6 bg-white dark:bg-gray-800/50 dark:bg-gradient-to-bl from-gray-700/50 via-transparent dark:ring-1 dark:ring-inset dark:ring-white/5 rounded-lg shadow-2xl shadow-gray-500/20 dark:shadow-none flex motion-safe:hover:scale-[1.01] transition-all duration-250 focus:outline focus:outline-2 focus:outline-red-500"
          >
            <div>
              <h2
                class="mt-6 text-2xl font-semibold text-gray-900 dark:text-white"
              >
                Vibrant Ecosystem
              </h2>

              <p class="mt-4 text-gray-500 dark:text-gray-400 leading-relaxed">
                Laravel's robust library of first-party tools and libraries,
                such as
                <a
                  href="https://forge.laravel.com"
                  class="underline hover:text-gray-700 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                  >Forge</a
                >,
                <a
                  href="https://vapor.laravel.com"
                  class="underline hover:text-gray-700 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                  >Vapor</a
                >,
                <a
                  href="https://nova.laravel.com"
                  class="underline hover:text-gray-700 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                  >Nova</a
                >, and
                <a
                  href="https://envoyer.io"
                  class="underline hover:text-gray-700 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                  >Envoyer</a
                >
                help you take your projects to the next level. Pair them with
                powerful open source libraries like
                <a
                  href="https://laravel.com/docs/billing"
                  class="underline hover:text-gray-700 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                  >Cashier</a
                >,
                <a
                  href="https://laravel.com/docs/dusk"
                  class="underline hover:text-gray-700 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                  >Dusk</a
                >,
                <a
                  href="https://laravel.com/docs/broadcasting"
                  class="underline hover:text-gray-700 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                  >Echo</a
                >,
                <a
                  href="https://laravel.com/docs/horizon"
                  class="underline hover:text-gray-700 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                  >Horizon</a
                >,
                <a
                  href="https://laravel.com/docs/sanctum"
                  class="underline hover:text-gray-700 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                  >Sanctum</a
                >,
                <a
                  href="https://laravel.com/docs/telescope"
                  class="underline hover:text-gray-700 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                  >Telescope</a
                >, and more.
              </p>
            </div>
          </div>
        </div>
      </div>

      <div
        class="flex justify-center mt-16 px-6 sm:items-center sm:justify-between"
      >
        <div class="text-center text-gray-500 dark:text-gray-400 sm:text-start">
          <div class="flex items-center gap-4">
            <a
              href="https://github.com/sponsors/taylorotwell"
              class="group inline-flex items-center hover:text-gray-700 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                class="-mt-px me-1 w-5 h-5 stroke-gray-400 dark:stroke-gray-600 group-hover:stroke-gray-600 dark:group-hover:stroke-gray-400"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12z"
                />
              </svg>
              Sponsor
            </a>
          </div>
        </div>

        <div
          class="ms-4 text-center text-gray-500 dark:text-gray-400 sm:text-end sm:ms-0"
        >
          Laravel v{{ laravelVersion }} (PHP v{{ phpVersion }})
        </div>
      </div>
    </div>
  </div>
</template>
