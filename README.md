HttpProxyMiddleware
-------
********

����һ��scrapy���м��middleware���û����� HTTP����
�����еĹ����У�HttpProxyMiddleware�����Զ���ȡ�µ�proxyes��ɾ����Ч��proxyes��

fetch_free_proxyes.py
---------------
*************
�ڸ�����Ѵ�����վ�ϻ�ȡ��ѵ�proxyes��
Usage
---------------
***********
### settings.py ###
	DOWNLOADER_MIDDLEWARES = {
	    'scrapy.downloadermiddlewares.downloadtimeout.DownloadTimeoutMiddleware': 350,
	    'scrapy.contrib.downloadermiddleware.retry.RetryMiddleware': 351,
	    # put this middleware after RetryMiddleware
	    'crawler.middleware.HttpProxyMiddleware': 999,
	}
	
	DOWNLOAD_TIMEOUT = 10   
### ����proxy ###
һ������£������ǵ�IP���������Ǿͱ���ʹ���µĴ���ȥ��½������һ���µ�����

	request.meta["change_proxy"] = True
��ʱ������ʹ�ô���Ҳ�᷵��һЩ��ЧHTML���롣������response�������������κ��쳣Ҳ��Ҫ����һ���µ�����

	request.meta["change_proxy"] = True
### spider.py ###
��spider��ȡ��ʱ�������ȡ����״̬�벻��200����ָ�����κ�״̬�뽫����Ϊ��Ч����������������

	website_possible_httpstatus_list = [404]
spider��ȡ���ܷ���404��Ӧ������������