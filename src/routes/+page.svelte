<script lang="ts">
    const FONTS = [
        "Ormin",
        "Doolittle Garamond",
        "Doolittle Garamond Italic",
        "Everson Mono",
        "Everson Mono Oblique",
    ] as const

    const DEFAULT_CONTENT = `𐑑𐑴 𐑣𐑨𐑥𐑪𐑯𐑦 𐑒𐑧 𐑛𐑧𐑤𐑨𐑥 𐑤𐑨𐑒 𐑟𐑨𐑛𐑧 𐑤𐑨𐑚𐑔𐑨𐑯𐑛𐑨𐑖 𐑮𐑪
𐑫 𐑒𐑧 𐑣𐑨𐑮𐑜𐑧𐑟 𐑯𐑨𐑑𐑨𐑝𐑪𐑯 𐑘𐑪𐑓𐑑 𐑣𐑨𐑥𐑪𐑯𐑨𐑯𐑛𐑨𐑖 𐑮𐑪
`

    let currentFont = $state("Ormin")
</script>

<div class="container max-w-prose py-4">
    <select
        bind:value={currentFont}
        class="border h-12 w-full border-gray-800 px-4 appearance-none flex items-center"
    >
        {#each FONTS as font}
            <option
                value={font}
                class="bg-background text-foreground flex gap-4 px-4 py-2 border-gray-800 not-last:border-b-0 hover:bg-gray-900 border"
            >
                {font}
            </option>
        {/each}
    </select>
</div>

<hr class="border-gray-900" />

<label>
    <div class="container px-0 max-w-prose">
        <textarea
            class="field-sizing-content w-full resize-none p-4 text-xl h-[calc(100vh-(var(--spacing)*12)-(var(--spacing)*4))]"
            value={DEFAULT_CONTENT}
            style:font-family={currentFont}></textarea>
    </div>
</label>

<style>
    select,
    ::picker(select) {
        appearance: base-select;
    }
    select::picker-icon {
        content: "🔻";
        filter: grayscale(1);
    }
    ::picker(select) {
        border: none;
    }
    ::picker(select) {
        top: calc(anchor(bottom) - 1px);
    }
</style>
