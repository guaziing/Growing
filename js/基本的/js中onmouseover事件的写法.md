### js中onmouseover事件的写法

    touxiang.onmouseover = rollTime;
	function rollTime() {
	  console.log("hover")
	  setTimeout(roll, 500);
	}