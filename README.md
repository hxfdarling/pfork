# pfork
用于在后台运行程序中启动一个进程执行相应的脚本

# Installation

	npm install pfork --save
	
# Usage
	var p = require('pfork');
	var options = {
		script: '/User/xxx/test/script.js', //必填
		value: '/User/xxx/test/server.js',  //可选
		//其它字段
	};
	p.fork(options, function(err, data, child) {
		//启动结束
		//child.on('data', function(data) {});
		//child.sendData(data);
	});
	
/User/xxx/test/script.js

	//options与fork的options字段一致
	module.exports = function(options, callback) {
		//do sth
		// process.sendData(data);
		callback(err, data);
	}；
	
kill process：

	p.kill({
		script: '/User/xxx/test/script.js',
		value: '/User/xxx/test/server.js'
	});