<template>
	<div class="bruce flex-ct-y" data-title="使用attr()抓取用户属性">
		<a class="hover-tips" href="https://www.baidu.com" data-msg="Hello World">提示框</a>
		<a class="hover-tips" href="https://www.baidu.com"></a>
	</div>
</template>

<style lang="scss" scoped>
.hover-tips {
	position: relative;
	padding: 0 20px;
	border-radius: 10px;
	height: 40px;
	background-color: #66f;
	line-height: 40px;
	color: #fff;
	&::after {
		position: absolute;
		left: 0;
		top: 0;
		border-radius: 5px;
		width: 100%;
		height: 100%;
		background-color: rgba(#000, .5);
		opacity: 0;
		text-align: center;
		font-size: 12px;
		content: attr(data-msg);
		transition: all 300ms;
	}
	&:hover::after {
		left: calc(100% + 20px);
		opacity: 1;
	}
	&[href]:empty::before {
		content: attr(href);
	}
	&[href]:empty:hover::after {
		display: none;
	}
	& + .hover-tips {
		margin-top: 10px;
	}
}
</style>