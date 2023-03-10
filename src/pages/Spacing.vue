<script setup>
  // Note there's a way we can just import these globally so we don't have to do it in every page
  import Box from '../components/Box.vue'
  import Container from '../components/Container.vue'
  import WidthController from '../components/WidthController.vue'

  const exampleClasses = 'p-4 rounded-2 text-white flex items-center justify-center'
</script>
<style>

  /* Support, yay or nay? They are nice */
  /* Same effect as -m-4 on parent and m-4 on children */ 
  .space-x-4 > * + * {
    margin-left: 1rem; 
  }
  .space-y-4 > * + * {
    margin-top: 1rem; 
  }
  .space-x-reverse > * + * {	
    --w-space-x-reverse: 1;
  }
</style>
<template>

  <h1>Basic usage</h1>
  <container>
    <div class="flex flex-wrap items-start justify-center text-white text-sm font-bold leading-6 -mx-5">
      <div class="flex items-start">
        <div class="flex-none px-5">
          <div class="bg-purple-500 shadow-lg rounded-lg overflow-hidden">
            <box striped class="h-6 rounded-t-lg" fg-color="var(--tw-white-fg)"></box>
            <div class="p-4">pt-6</div>
          </div>
        </div>
        <div class="flex-none px-5 pt-6">
          <div class="flex bg-purple-500 shadow-lg rounded-lg overflow-hidden">
            <div class="flex-none p-4">pr-4</div>
            <box striped class="flex-none w-4" fg-color="var(--tw-white-fg)" ></box>
          </div>
        </div>
      </div>
      <div class="flex items-start">
        <div class="flex-none px-5 pt-6">
          <div class="bg-purple-500 shadow-lg rounded-lg overflow-hidden">
            <div class="p-4">pb-8</div>
            <box striped class="h-8" fg-color="var(--tw-white-fg)"></box>
          </div>
        </div>
        <div class="flex-none flex px-5 pt-6">
          <div class="flex bg-purple-500 shadow-lg rounded-lg overflow-hidden">
            <box striped class="flex-none w-2" fg-color="var(--tw-white-fg)"></box>
            <div class="flex-none p-4">pl-2</div>
          </div>
        </div>
      </div>
    </div>
  </container>
  <h2>Code example</h2>
  <container>
    <!-- Placeholder for a syntax-higlighter -->
    <syntax-highlighter>
      <!--
        <div class="pt-6 ...">pt-6</div>
        <div class="pr-4 ...">pr-4</div>
        <div class="pb-8 ...">pb-8</div>
        <div class="pl-2 ...">pl-2</div>
      -->
    </syntax-highlighter>
  </container>
  <h1>Horizontal Padding</h1>
  <container>
    <dev class="relative rounded-xl overflow-auto p-8">
      <div class="flex justify-center font-mono text-white text-sm font-bold leading-6">
        <div class="bg-indigo-500 rounded-lg shadow-lg overflow-hidden flex">
          <box striped class="w-8" fg-color="var(--tw-white-fg)"></box>
          <div class="p-4">px-8</div>
          <box striped class="w-8" fg-color="var(--tw-white-fg)"></box>
        </div>
      </div>
    </dev>
  </container>

  <h2>Code example</h2>
  <container>
    <syntax-highlighter>
      <!--
        <div class="px-8 ...">px-8</div>
      -->
    </syntax-highlighter>
  </container> 
  

  <h1>Vertical padding</h1>
  <container>
    <div class="relative rounded-xl overflow-auto p-8">
      <div class="flex justify-center font-mono text-white text-sm font-bold leading-6">
        <div class="bg-pink-500 rounded-lg shadow-lg overflow-hidden">
          <box striped class="h-8" fg-color="var(--tw-white-fg)"></box>
          <div class="p-4">py-8</div>
          <box striped class="h-8" fg-color="var(--tw-white-fg)"></box>
        </div>
      </div>
    </div>
  </container>

  <h2>Code example</h2>
  <container>
    <syntax-highlighter>
      <!--
        <div class="px-8 ...">px-8</div>
      -->
    </syntax-highlighter>
  </container> 



  <h1>Padding to all sides</h1>
  <container>
    <div class="relative rounded-xl overflow-auto p-8">
      <div class="flex justify-center font-mono text-white text-sm font-bold leading-6">
        <div class="bg-violet-500 rounded-lg shadow-lg ">
          <box striped class="p-8" fg-color="var(--tw-white-fg)">
            <div class="bg-violet-500 p-4">p-8</div>
          </box>
        </div>
      </div>
    </div>
  </container>

  <h2>Code example</h2>
  <container>
    <syntax-highlighter>
      <!--
        <div class="p-8 ...">p-8</div>
      -->
    </syntax-highlighter>
  </container>

  
  <h1>Add margin to a single side</h1>
  <container bleeding>
    <div class="relative -my-8 -mx-4 rounded-xl overflow-auto">
      <div class="relative font-mono text-white text-sm font-bold leading-6 h-56">
        <div class="absolute top-0 left-1/2 -translate-x-1/2 md:-ml-24">
          <box striped class="flow-root rounded-b-lg" fg-color="var(--tw-purple-fg)" bg-color="var(--tw-purple-bg)" >
            <div class="bg-purple-500 rounded-lg shadow-lg p-4 mt-6">mt-6</div>
          </box>
        </div>
        <div class="absolute right-0 top-1/2 -translate-y-1/2">
          <box striped class="flow-root rounded-l-lg" fg-color="var(--tw-purple-fg)" bg-color="var(--tw-purple-bg)" >
            <div class="flex-none bg-purple-500 rounded-lg shadow-lg p-4 mr-4">mr-4</div>
          </box>
        </div>
        <div class="absolute bottom-0 left-1/2 -translate-x-1/2 md:ml-24">
          <box striped class="flow-root rounded-t-lg" fg-color="var(--tw-purple-fg)" bg-color="var(--tw-purple-bg)" >
            <div class="bg-purple-500 rounded-lg shadow-lg p-4 mb-8">mb-8</div>
          </box>
        </div>
        <div class="absolute left-0 top-1/2 -translate-y-1/2">
          <box striped class="flow-root rounded-r-lg" fg-color="var(--tw-purple-fg)" bg-color="var(--tw-purple-bg)" >
            <div class="flex-none bg-purple-500 rounded-lg shadow-lg p-4 ml-2">ml-2</div>
          </box>
        </div>
      </div>
    </div>
  </container>
  <h2>Code example</h2>
  <container>
    <syntax-highlighter>
      <!--
      <div class="mt-6 ...">mt-6</div>
      <div class="mr-4 ...">mr-4</div>
      <div class="mb-8 ...">mb-8</div>
      <div class="ml-2 ...">ml-2</div>
      -->
    </syntax-highlighter>
  </container> 

  <h1>Add horizontal margin</h1>
  <container>
    <div class="relative rounded-xl overflow-auto p-8">
      <div class="flex justify-center font-mono text-white text-sm font-bold leading-6">
        <box striped class="rounded-lg" fg-color="var(--tw-indigo-fg)" bg-color="var(--tw-indigo-bg)">
          <div class="bg-indigo-500 rounded-lg shadow-lg p-4 mx-8">mx-8</div>
        </box>
      </div>
    </div>
  </container>
  <h2>Code example</h2>
  <container>
    <syntax-highlighter>
      <!--
        <div class="mx-8 ...">mx-8</div>
      -->
    </syntax-highlighter>    
  </container>

  <h1>Add vertical margin</h1>
  <container>
    <div class="relative rounded-xl overflow-auto p-8">
      <div class="flex justify-center font-mono text-white text-sm font-bold leading-6">
        <box striped class="flow-root rounded-lg" fg-color="var(--tw-pink-fg)" bg-color="var(--tw-pink-bg)">
          <div class="bg-pink-500 rounded-lg shadow-lg p-4 my-8">my-8</div>
        </box>
      </div>
    </div>
  </container>
  <h2>Code example</h2>
  <container>
    <syntax-highlighter>
      <!--
        <div class="my-8 ...">my-8</div>
      -->
    </syntax-highlighter>    
  </container>

  <h1>Add margin to all sides</h1>
  <container>
    <div class="relative rounded-xl overflow-auto p-8">
      <div class="flex justify-center font-mono text-white text-sm font-bold leading-6">
        <box striped class="flow-root rounded-lg" fg-color="var(--tw-blue-fg)" bg-color="var(--tw-blue-bg)">
          <div class="bg-blue-500 rounded-lg shadow-lg p-4 m-8">m-8</div>
        </box>
      </div>
    </div>
  </container>
  <h2>Code example</h2>
  <container>
    <syntax-highlighter>
      <!--
        <div class="m-8 ...">m-8</div>
      -->
    </syntax-highlighter>    
  </container>

  <h1>Using negative values</h1>
  <container>
    <div class="relative rounded-xl overflow-auto p-8">
      <div class="flex justify-center font-mono text-white text-sm font-bold leading-6">
        <div class="flex flex-col items-center">
          <div class="relative w-36 h-16 bg-sky-400/20 border border-sky-700/10 rounded-md overflow-hidden"></div>
          <div class="relative -mt-8 bg-sky-500 rounded-md flex items-center justify-center p-4 shadow-lg">-mt-8</div>
        </div>
      </div>
    </div>
  </container>
  <h2>Code example</h2>
  <container>
    <syntax-highlighter>
      <!--
        <div class="w-36 h-16 bg-sky-400 opacity-20 ..."></div>
        <div class="-mt-8 bg-sky-300 ...">-mt-8</div>
      -->
    </syntax-highlighter>    
  </container>

  <h1>Add horizontal space between children</h1>
  <container>
    <div class="relative rounded-xl overflow-auto p-8">
      <div class="flex justify-center font-mono text-white text-sm font-bold leading-6">
        <box striped class="flex space-x-4 bg-stripes-fuchsia rounded-lg" fg-color="var(--tw-fuchsia-fg)" bg-color="var(--tw-fuchsia-bg)">
          <div class="w-14 h-14 flex items-center justify-center shadow-lg rounded-lg bg-fuchsia-500">01</div>
          <div class="w-14 h-14 flex items-center justify-center shadow-lg rounded-lg bg-fuchsia-500">02</div>
          <div class="w-14 h-14 flex items-center justify-center shadow-lg rounded-lg bg-fuchsia-500">03</div>
        </box>
      </div>
    </div>
  </container>
  <h2>Code example</h2>
  <container>
    <syntax-highlighter>
      <!--
        <div class="flex space-x-4 ...">
          <div>01</div>
          <div>02</div>
          <div>03</div>
        </div>
      -->
    </syntax-highlighter>    
  </container>

  <h1>Add vertical space between children</h1>
  <container>
    <div class="relative rounded-xl overflow-auto p-8">
      <div class="flex flex-col justify-center text-center w-full font-mono text-white text-sm font-bold leading-6">
        <box striped class="flex flex-col space-y-4 bg-stripes-indigo rounded-lg" fg-color="var(--tw-indigo-fg)" bg-color="var(--tw-indigo-bg)">
          <div class="p-4 flex items-center justify-center shadow-lg rounded-lg bg-indigo-500">01</div>
          <div class="p-4 flex items-center justify-center shadow-lg rounded-lg bg-indigo-500">02</div>
          <div class="p-4 flex items-center justify-center shadow-lg rounded-lg bg-indigo-500">03</div>
        </box>
      </div>
    </div>
  </container>
  <h2>Code example</h2>
  <container>
    <syntax-highlighter>
      <!--
        <div class="flex flex-col space-y-4 ...">
          <div>01</div>
          <div>02</div>
          <div>03</div>
        </div>
      -->
    </syntax-highlighter>    
  </container>

  <h1>Reversing children order</h1>
  <container>
    <div class="relative rounded-xl overflow-auto p-8">
      <div class="flex justify-end font-mono text-white text-sm font-bold leading-6">
        <box striped class="flex flex-row-reverse space-x-4 space-x-reverse rounded-lg" fg-color="var(--tw-cyan-fg)" bg-color="var(--tw-cyan-bg)">
          <div class="w-14 h-14 flex items-center justify-center shadow-lg rounded-lg bg-cyan-500">01</div>
          <div class="w-14 h-14 flex items-center justify-center shadow-lg rounded-lg bg-cyan-500">02</div>
          <div class="w-14 h-14 flex items-center justify-center shadow-lg rounded-lg bg-cyan-500">03</div>
        </box>
      </div>
    </div>
  </container>
  <h2>Code example</h2>
  <container>
    <syntax-highlighter>
      <!--
        <div class="flex flex-row-reverse space-x-4 space-x-reverse ...">
          <div>01</div>
          <div>02</div>
          <div>03</div>
        </div>
      -->
    </syntax-highlighter>    
  </container>

</template>
