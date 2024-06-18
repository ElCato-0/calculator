<script lang="ts">
    import MinusIcon from "$lib/icons/Minus.svelte";
    import DivisionIcon from "$lib/icons/Division.svelte";
    import MultiplyIcon from "$lib/icons/Multiply.svelte";
    import PlusIcon from "$lib/icons/Plus.svelte";
    import BackSpaceIcon from "$lib/icons/Backspace.svelte";

    function addToEquation(value: string) {
        equation += value;
    }

    // TODO: fix remove spaces
    function backspace() {
        equation = equation.substring(0, equation.length - 1);
    }

    function clear() {
        equation = "";
    }

    let equation: string = "";
</script>

<svelte:head>
    <title>الة حاسبة</title>
</svelte:head>

<div
    class="bg-white rounded-3xl grid grid-cols-4 gap-1 p-6 font-semibold text-xl shadow-xl"
>
    <!-- TODO: fix overflowing numbers -->
    <div
        class="bg-blue-500 rounded-full col-span-4 h-12 flex items-center px-4 mb-2 text-white"
    >
        {equation}
    </div>
    <button on:click={() => addToEquation(" / 100")} class="bg-[#f3f6fc]">
        %
    </button>
    <button on:click={() => backspace()} class="bg-[#f3f6fc]">
        <BackSpaceIcon />
    </button>
    <button class="bg-[#f3f6fc]"> CE </button>
    <button on:click={() => clear()} class="bg-[#1f2b54] text-white">
        C
    </button>
    <button on:click={() => addToEquation("7")}> 7 </button>
    <button on:click={() => addToEquation("8")}> 8 </button>
    <button on:click={() => addToEquation("9")}> 9 </button>
    <button
        on:click={() => addToEquation(" - ")}
        class="bg-[#fd3f59] text-white"
    >
        <MinusIcon />
    </button>
    <button on:click={() => addToEquation("4")}> 4 </button>
    <button on:click={() => addToEquation("5")}> 5 </button>
    <button on:click={() => addToEquation("6")}> 6 </button>
    <button
        on:click={() => addToEquation(" / ")}
        class="bg-[#2285fd] text-white"
    >
        <DivisionIcon />
    </button>
    <button on:click={() => addToEquation("1")}> 1 </button>
    <button on:click={() => addToEquation("2")}> 2 </button>
    <button on:click={() => addToEquation("3")}> 3 </button>
    <button
        on:click={() => addToEquation(" * ")}
        class="bg-[#f9c80e] text-white"
    >
        <MultiplyIcon />
    </button>
    <button on:click={() => addToEquation(".")}> . </button>
    <button on:click={() => addToEquation("0")}> 0 </button>
    <button> = </button>
    <button
        on:click={() => addToEquation(" + ")}
        class="bg-[#63dc74] text-white"
    >
        <PlusIcon />
    </button>
</div>
