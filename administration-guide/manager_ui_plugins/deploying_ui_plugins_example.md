# 示例部署用户界面插件

按照以下的示例可以在你登陆 oVirt 企业级虚拟化管理门户时运行一个 **Hello World！** 的用户界面插件程序。


**实现一个 Hello World! 插件**

1. 在管理端上创建一个插件描述文件：**/usr/share/ovirt-engine/ui-plugins/helloWorld.json** 内容如下：

   ```
   {
       "name": "HelloWorld",
       "url": "/webadmin/webadmin/plugin/HelloWorld/start.html",
       "resourcePath": "hello-files"
   }
   ```

2. 通过在管理端上创建如下文件
   **/usr/share/ovirt-engine/ui-plugins/hello-files/start.html**
   来创建插件主页：

   ```
   <!DOCTYPE html><html><head>
   <script>
       var api = parent.pluginApi('HelloWorld');
       api.register({
       UiInit: function() { window.alert('Hello world'); }
       });
       api.ready();
   </script>
   </head><body></body></html>
   ```

如果你成功地实现了 **Hello World！**
插件，那么你在登陆管理门户时你将看到如下的界面：

![成功部署的 Hello World! 插件](images/oVirt_Manager_UI_Plugin-A_Successful_Implementation_Of_Hello_World_Plugin.png)
