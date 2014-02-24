## jQuery��html(code)���������code����<script>���������Զ�ִ��
```js
(function() {
  function evalScript(elem) {
    var data = (elem.text || elem.textContent || elem.innerHTML || "" ),
        head = document.getElementsByTagName("head")[0] ||
                  document.documentElement,
        script = document.createElement("script");

    script.type = "text/javascript";
    try {
      // doesn't work on ie...
      script.appendChild(document.createTextNode(data));
    } catch(e) {
      // IE has funky script nodes
      script.text = data;
    }

    head.insertBefore(script, head.firstChild);
    head.removeChild(script);
  };

  $.fn.htmlEx = function(code) {
    var $scripts = this.html(code).find('script'),
        scripts = [],
        type;
    $scripts.each(function(script) {
      type = $(script).attr('type');
      if (type && type !== 'text/javascript') {
        return;
      }

      evalScript(script);
    });

    return this;
  }
})();
'''
