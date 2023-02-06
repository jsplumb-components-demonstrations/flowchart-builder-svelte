
<script>
    import {onMount} from "svelte"
    import {FlowchartComponent, PaletteComponent, InspectorComponent} from "@jsplumb-components/flowchart-svelte"

    let flowchartBuilder

    onMount(async () => {
        flowchartBuilder.loadUrl("./copyright.json", () => {
            flowchartBuilder.zoomToFit()
        })
    })

</script>


<div id="canvas">
    <FlowchartComponent id="myFlowchart" bind:this={flowchartBuilder}/>
</div>

<div id="rhs">
    <PaletteComponent flowchartId="myFlowchart"></PaletteComponent>
    <InspectorComponent flowchartId="myFlowchart"></InspectorComponent>
</div>

