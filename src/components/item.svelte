<script>
  import Transition from 'svelte-class-transition';
  import { slide } from 'svelte/transition';
    let toggle = false
    export let item;
    export let dummyItemsCount;
</script>
<main>
    <h2>
        <button on:click={()=> toggle = !toggle} type="button" class="flex {toggle ? 'bg-blue-50 text-blue-500' : ''} {dummyItemsCount == item.id ? 'border-t-0' : ''} {item.id == 1 ? 'border-b-0' : ''} font-serif text-lg font-thin justify-between items-center p-5 w-full text-left text-black focus:ring ring-blue-200 focus:border-blue-200">
          <span>{item.title}</span>
          <Transition
            {toggle}
            transitions="transition transform"
            inTransition="ease-out duration-200"
            inState="rotate-0"
            onState="-rotate-180 text-blue-500"
            outTransition="ease-in duration-200"
          >
          <svg class="w-8 h-8 font-serif shrink-0" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd"></path></svg>
        </Transition>
        </button>
      </h2>
          {#if toggle}
          <div transition:slide|local>
          <div class="p-5 border-gray-200">
            <p class="mb-2 text-black text-lg">{@html item.content}
              </p>
          </div>
        </div>
        {/if}
</main>