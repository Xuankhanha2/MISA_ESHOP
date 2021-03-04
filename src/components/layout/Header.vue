<template>
    <div class="header">
        <div class="header_left">
            <ul>
                <li><span class="current_page">Tài sản</span></li>
                <li>/ <span class="other_page">Danh mục tài sản</span></li>
            </ul>
        </div>
        <div class="header_right">

        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            
        }
    },
}
</script>
<style>
    .header{
        width: 100%;
        height: 60px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        border-bottom: 1px solid #bbbbbb;
    }
    .header ul{
        padding: 24px;
        list-style: none;
        display: flex;
    }
    .current_page{
        color: #00abfe;
        cursor: pointer;
        font-size: 16px;
        padding-left: 4px;
    }
    .other_page{
        font-size: 16px;
        padding-left: 4px;
        cursor: pointer;
    }
</style>