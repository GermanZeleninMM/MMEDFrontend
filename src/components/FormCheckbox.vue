<template>
    <div class="formcheckbox">
        <div>
            <input type="checkbox" id="jack" value="Джек" v-model="checkedNames" class="checkbox">
            <label for="jack">В России</label>
        </div>

        <div>
            <input type="checkbox" id="john" value="Джон" v-model="checkedNames" class="checkbox">
            <label for="john">В мире</label>
        </div>

        <div>
            <input type="checkbox" id="mike" value="Майк" v-model="checkedNames" class="checkbox">
            <label for="mike">Важное</label>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style>
.checkbox {
	position: absolute;
	z-index: -1;
	opacity: 0;
	margin: 10px 0 0 20px;
}
.checkbox + label {
	position: relative;
	padding: 0 0 0 60px;
	cursor: pointer;
}
.checkbox + label:before {
	content: '';
	position: absolute;
	top: -4px;
	left: 0;
	width: 50px;
	height: 26px;
	border-radius: 13px;
	background: #CDD1DA;
	box-shadow: inset 0 2px 3px rgba(0,0,0,.2);
	transition: .2s;
}
.checkbox + label:after {
	content: '';
	position: absolute;
	top: -2px;
	left: 2px;
	width: 22px;
	height: 22px;
	border-radius: 10px;
	background: #FFF;
	box-shadow: 0 2px 5px rgba(0,0,0,.3);
	transition: .2s;
}
.checkbox:checked + label:before {
	background: #002c85;
}
.checkbox:checked + label:after {
	left: 26px;
}

.formcheckbox {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    padding: 10px 15px;
    margin-top: 15px;
}
</style>