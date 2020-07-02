# postman-jmeter-example

[Automatizing a Postman test with JMeter](https://apiumhub.com/tech-blog-barcelona/automatizing-postman-test-jmeter/)

[PostMan API 示例](https://github.com/DannyDainton/postman-ci-pipeline-example)

[JMeter GitHub Examples](https://github.com/dariachen/JmeterExample/blob/master/.travis.yml)

[postman2jmx](https://github.com/Loadium/postman2jmx)

[JMeter Bootstrap](https://github.com/cfpb/jmeter-bootstrap)

```bash
jmeter -n -t src/wdsm.jmx -l result.jtl
```


```javascript
pm.test("response is ok", function () {
    pm.response.to.have.status(200);
});

pm.test("response must be valid and have a body", function () {
     pm.response.to.be.ok;
     pm.response.to.be.withBody;
     pm.response.to.be.json;
});

pm.test("首页 API 应该返回正确的 top, hot, new 长度", function () {
    pm.expect(pm.response.json().top.length).to.eql(3);
    pm.expect(pm.response.json().hot.length).to.eql(3);
    pm.expect(pm.response.json().new.length).to.eql(6);
});

pm.test("首页 API 的 top 字段应该返回正确字段名", function () {
    pm.expect(Object.keys(pm.response.json().top[0])).to.eql(["id","user","user_bio","title","slug","description","updated","content","featured_image","categories","related_posts"]);
});

pm.test("首页 API 的 new 的第一个值的 ID 应该是 195", function () {
    pm.expect(pm.response.json().new[0].id).to.eql(195);
});
```

