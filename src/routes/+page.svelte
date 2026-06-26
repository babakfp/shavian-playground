<script lang="ts">
    const FONTS = [
        "Ormin",
        "Doolittle Garamond",
        "Doolittle Garamond Italic",
    ] as const

    const DEFAULT_CONTENT = `𐑑𐑴 𐑣𐑨𐑥𐑪𐑯𐑦 𐑒𐑧 𐑛𐑧𐑤𐑨𐑥 𐑤𐑨𐑒 𐑟𐑨𐑛𐑧 𐑤𐑨𐑚𐑔𐑨𐑯𐑛𐑨𐑖 𐑮𐑪
𐑫 𐑒𐑧 𐑣𐑨𐑮𐑜𐑧𐑟 𐑯𐑨𐑑𐑨𐑝𐑪𐑯 𐑘𐑪𐑓𐑑 𐑣𐑨𐑥𐑪𐑯𐑨𐑯𐑛𐑨𐑖 𐑮𐑪
`

    let currentFont = $state("Ormin")
</script>

<label class="container py-4 block">
    <select
        bind:value={currentFont}
        class="border h-12 w-full border-gray-800 px-4 appearance-none"
    >
        {#each FONTS as font}
            <option value={font}>
                {font}
            </option>
        {/each}
    </select>
</label>

<main class="container px-0">
    <textarea
        class="field-sizing-content w-full resize-none border-t border-gray-900 p-4 text-xl h-[calc(100vh-(var(--spacing)*12)-(var(--spacing)*4))]"
        value={DEFAULT_CONTENT}
        style:font-family={currentFont}></textarea>
</main>
