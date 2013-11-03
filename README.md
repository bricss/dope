Dope.js
=======

The aerogel-weight & dead-simple resource loader.

Usage:
~~~ javascript
if (/msie\s[1-8]\./.test(navigator.userAgent.toLowerCase())) {
  (document.body.className += ' ' + 'fallback') || (document.getElementsByTagName('body')[0].className += ' ' + 'fallback');
  dope('//somewhe.re/assets/js/augment.min.js', function(ev) {
    console.log('WOOP!');
    dope('//somewhe.re/assets/js/selectivizr.min.js', function(ev) {
      console.log('WOOP!');
    });
  });
}

if (/^.*(urn$)/i.test(window.location.href)) {
  dope('//somewhe.re/assets/js/common.min.js', function(ev) {
    console.log('WOOP!');
  }, 1000, 5000);
}

dope('//somewhe.re/assets/css/layout.css', function(ev) {
  console.log('WOOP!');
}, 1000, 5000);

dope(['//somewhe.re/assets/js/core.min.js', '//somewhe.re/assets/js/app.min.js'], function(ev) {
  console.log('WOOP!');
});

dope('//somewhe.re/assets/js/core.min.js', function(ev) {
  console.log('WOOP!');
}).dope('//somewhe.re/assets/js/app.min.js', function(ev) {
  console.log('WOOP!');
});
~~~
