<template>
    <div class="header">
        <div class="header_left">
            <ul>
                <li><span class="current_page">Tài sản</span></li>
                <li>/ <span class="other_page">Danh mục tài sản</span></li>
            </ul>
        </div>
        <div class="header_right">
            <div class="right_header_title">
                Sở tài chính
            </div>
            <select name="year_select" id="select_year">
                <option value="2021">Năm 2020</option>
                <option value="2021">Năm 2019</option>
                <option value="2021">Năm 2018</option>
                <option value="2021">Năm 2017</option>
            </select>
            <div class="help_n_notify">
                <div class="help_button"></div>
                <div class="notify"></div>
            </div>

            <div class="account">
                <div class="avatar"></div>
                <div class="btn_extend"></div>
            </div>
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
    /* header left */
    .header_left{
        margin: 0px;
        padding: 0px;
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
    /* end header left */

    /* header right */
    .header_right{
        margin: 0px;
        display: flex;
        align-items: center;
    }
    .right_header_title{
        font-size: 16px;
        font-weight: bold;
        line-height: 35px;
        padding: 0px 12px;
    }
    #select_year{
        height: 35px;
        line-height: 35px;
        border: 1px solid #bbbbbb;
        border-radius: 4px;
        padding-left: 16px;
    }
    #select_year option{
        padding: left 12px;
        padding-right: 12px;
        line-height: 30px;
    }
    /* end header right */
</style>