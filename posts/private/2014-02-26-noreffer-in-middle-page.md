## Ϊʲô��Ҫ�м�ҳ
1. j.www.so.com �Ǳ��������Ͽɵ���Դ��new1.360.cn, new2.so.com ��Щ�����Ĳ����������Ͽɵ���Դ����ʱ����ͨ�� j.www.so.com �� referrer �޸�Ϊ j.www.so.com���ﵽ��Դͳ�Ƶ�Ŀ�ġ�

## ��תʹ���м�ҳ�ĺô�
1. ���ϣ��ɷ���ʵ����Դͳ��
2. ���ʵ�� noreferrer ���ܣ����������߼��������м�ҳ��������ÿ��ҳ������һ��JavaScript����

## ���ʵ��
```
<iframe src='javascript:window.open("http://tieba.baidu.com/f?kw=%BA%C3", "_top");' style='display:none;'></iframe>
```

## �к�����
1. GBK�������������루IE6~IE11/Chrome���Զ����д�Bug��

## �޸����� 
```
(function() {
var url = 'http://tieba.baidu.com/f?kw=%BA%C3';
try {
    var iframe = document.createElement('iframe');
    iframe.style.display = 'none';
    iframe.src="about:blank";
    document.body.appendChild(iframe);
    iframe.contentWindow.open(url, '_top');
} catch(e) {
    window.location.replace(url);
}
})();
```

## ��������
1. iframe��srcΪJavaScriptαЭ��ķ�ʽ�����URL��GBK���룬�� Firefox����ת�����Թ� 27.0.1 ��

## rel="noreferrer" ��֧����
1. Firefox 
