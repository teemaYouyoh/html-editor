<template>
    <header class="header">
        <div class="header_wrapper">
        <h3 class="header_label">html editor</h3>

        </div>
    </header>
</template>

<script>
export default {
    
}
</script>

<style scoped>
.header{
    /* height: 70px;
    width: 100%;
    box-sizing: border-box;
    max-width: 1440px;
    padding: 0px 20px;
        display: flex;
    align-items: center; */
    position: absolute;
width: 1440px;
height: 70px;
left: 0px;
top: 0px;
}

.header_wrapper{
display: flex;
flex-direction: row;
padding: 0px;

position: absolute;
width: 119px;
height: 27px;
left: 31px;
top: 21px;
}

.header_label{
    font-size: 18px;
    color: #252A32;
    font-family: Roboto;
    font-weight: 500;
    line-height: 150%;
/* identical to box height, or 27px */
letter-spacing: 0.02em;
    text-transform: uppercase;
}
</style>