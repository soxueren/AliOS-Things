
## #RTC API

<div class="bi-table">
  <table>
    <colgroup>
      <col width="90px" />
      <col width="90px" />
    </colgroup>
    <tbody>
      <tr>
        <td rowspan="1" colSpan="1">
          <div data-type="p">API</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">说明</div>
        </td>
      </tr>
      <tr>
        <td rowspan="1" colSpan="1">
          <div data-type="p">RTC.open()</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p"><span data-type="color" style="color:rgb(245, 34, 45)">功能：</span>打开rtc</div>
          <div data-type="p"><span data-type="color" style="color:rgb(245, 34, 45)">参数：</span> 无</div>
          <div data-type="p"><span data-type="color" style="color:rgb(245, 34, 45)">返回值：</span>0=ok other=fail</div>
        </td>
      </tr>
      <tr>
        <td rowspan="1" colSpan="1">
          <div data-type="p">RTC.close()</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p"><span data-type="color" style="color:rgb(245, 34, 45)">功能：</span>关闭rtc</div>
          <div data-type="p"><span data-type="color" style="color:rgb(245, 34, 45)">参数：</span> 无;</div>
          <div data-type="p"><span data-type="color" style="color:rgb(245, 34, 45)">返回值：</span>0=ok other=fail</div>
          <div data-type="p"></div>
        </td>
      </tr>
      <tr>
        <td rowspan="1" colSpan="1">
          <div data-type="p">RTC.setTime(obj)</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p"><span data-type="color" style="color:rgb(245, 34, 45)">功能：</span>配置rtc时间</div>
          <div data-type="p"><span data-type="color" style="color:rgb(245, 34, 45)">参数：</span> obj:时间值对象，包含了年月日时分秒;  </div>
          <div data-type="p">obj：时间参数，包含了时分秒年月;</div>
          <div data-type="p"></div>
          <div data-type="p"><span data-type="color" style="color:rgb(245, 34, 45)">返回值：</span>0=ok other=fail</div>
          <div data-type="p"></div>
        </td>
      </tr>
      <tr>
        <td rowspan="1" colSpan="1">
          <div data-type="p">RTC.getTime()</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p"><span data-type="color" style="color:rgb(245, 34, 45)">功能：</span>读取rtc时间</div>
          <div data-type="p"><span data-type="color" style="color:rgb(245, 34, 45)">参数：</span> 无; </div>
          <div data-type="p"><span data-type="color" style="color:rgb(245, 34, 45)">返回值：</span>json对象，包含了年月日时分秒;</div>
        </td>
      </tr>
    </tbody>
  </table>
</div>



## #板级配置参数
无

## #板级配置示范
无

## #DeveloperKit之DS1307

### #硬件
1)developerkit开发板；
2)ds1307模块;


![3.jpg | left | 683x337](https://cdn.yuque.com/lark/0/2018/jpeg/66207/1524935841454-17005552-474c-43f9-be7d-3a3da2cf5d2a.jpeg "")


### #接线
developerKit 的VCC引脚连接DS1307模块的VCC；
developerKit 的GND引脚连接DS1307模块的GND；
developerKit 的SCL引脚连接DS1307模块的SCL；
developerKit 的SDA引脚连接DS1307模块的SDA；

### #配置
无

### #代码
```javascript
print('start rtc test.....................');
RTC.open();
RTC.setTime({'year':18,'month':4,'day':29,'hour':12,'minute':57,'second':0});
setInterval(function() {
	var rtcdata = RTC.getTime(); 
	console.log(rtcdata.year+'/'+rtcdata.month+'/'+rtcdata.day+':'+rtcdata.second);	
}, 2000);
print('start end test.....................');
```


### #现象


![4.jpg | left | 275x278](https://cdn.yuque.com/lark/0/2018/jpeg/66207/1524936026000-26f3b2d4-46f1-491c-84fa-eae5b6487a36.jpeg "")



## #ESP32之RTC

### #硬件
1)esp32Kit开发板


![1.png | left | 427x278](https://cdn.yuque.com/lark/0/2018/png/66207/1525918760569-51b534e0-f54d-45a2-bdc7-64adb8b22bcb.png "")



### #接线
无

### #配置
无

### #代码
```javascript
print('start rtc test.....................');
RTC.open();
RTC.setTime({'year':18,'month':4,'day':29,'hour':12,'minute':57,'second':0});
setInterval(function() {
	var rtcdata = RTC.getTime(); 
	console.log(rtcdata.year+'/'+rtcdata.month+'/'+rtcdata.day+':'+rtcdata.second);	
}, 2000);
print('start end test.....................');
```


### #现象
每间隔2秒打印一次时间。


![1.png | left | 269x198](https://cdn.yuque.com/lark/0/2018/png/66207/1525918819420-a6620aba-f3ca-417a-9fa9-93a83125702b.png "")



 