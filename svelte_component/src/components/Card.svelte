<div class="card">
    <div class="header">
        <slot name="header"></slot>
    </div>
    <div class="content">
        <slot name="content"></slot>
    </div>
    <div class="footer">
        <slot name="footer"></slot>
    </div>
</div>

<style>
    .card{
        width: 150px;
        height: 100px;
        background-color: aqua;
    }
</style>