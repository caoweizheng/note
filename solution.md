# 用promise async await 解决回调地狱问题 #
	let sblider = ()=>{
	    // 返回promise对象
	    return new Promise((resolve,reject)=>{
	        // request
	        // 服务器代理
	        request.get('https://www.hao123.com/?tn=93006350_hao_pg',(error,responsr,body)=>{
	            // 请求成功后执行这里
	            resolve(body);
	        })
	    })
	}
	
	// 用async替代then
	// 解决then()函数里面还是一个对调函数的问题
	
	let start = async () => {
	
	    // 这句代码的意思是等 await 后面的sblider()函数执行完成之后才执行后面的代码
	    // await 必须写在async()函数里面
	    // await 后面跟的一定是一个Promise对象
	    let body = await sblider();
	    // cheerio.load 相当于把body封装成jq对象返回
	    let $ = cheerio.load(body);
	
	    // 拿到body 中的所有a标签
	    $('a').each((idx,ele)=>{
	        // 获取到所有a标签的文本内容
	        let txt = $(ele).text();
	        // 写入本地,追加写入
	        fs.createWriteStream('alltext.txt',{'flags': 'a'}).write(txt + "----------",'UTF8');
	    })
	}
	
	start();
