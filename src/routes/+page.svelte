<script>
  import { contacts } from "../lib/contacts";
  import { data } from "./data";
  import snarkdown from "snarkdown";
</script>

<div class="hero min-h-screen" style="background-image: url('/img/bg.webp');">
  <div class="hero-overlay"></div>
  <div class="hero-content text-neutral-content text-center">
    <div class="max-w-md text-white">
      <h1 class="mb-5 text-6xl font-bold drop-shadow-md">Rino Vago</h1>
      <p class="mb-5 text-xl font-bold drop-shadow-md">
        Servizi di consulenza alberghiera
      </p>
    </div>
  </div>
</div>

<div
  id="servizi"
  class="min-h-screen flex flex-wrap justify-center align-center gap-3 p-11 mx-auto max-w-screen-lg"
>
  {#each data as row, index}
    <div class="my-4">
      <h1 class="text-3xl">{row.title}</h1>
      <div class="flex gap-1" class:flex-row-reverse={index % 2 == 0}>
        <div class="w-6/12" class:hidden={!row.img}>
          <img
            src="/img/{row.img ?? 0}.webp"
            alt={row.img}
            width="180"
            height="180"
          />
        </div>
        <div>
          {@html snarkdown(row.md)}
        </div>
      </div>
    </div>
  {/each}
</div>

<div
  id="contatti"
  class="grid lg:grid-cols-2 gap-3 p-11 mx-auto max-w-screen-lg"
>
  <div>
    <img src="/img/rino-vago.webp" alt="Rino Vago" />
  </div>
  <div class="text-center gap-5">
    <h1 class="text-3xl">Entriamo in contatto</h1>

    <div class="my-5">
      {#each contacts as c}
        <div class="my-4">
          <a
            href={c.url}
            target="_blank"
            class="btn btn-ghost btn-block mx-auto flex justify-between align-baseline flex-nowrap"
          >
            <img src="/img/{c.icon}.webp" alt="{c.title} icon" width="33" />
            <p>
              {c.title}
            </p>
            <p></p>
          </a>
        </div>
      {/each}
    </div>
  </div>
</div>
