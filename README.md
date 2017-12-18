# ServiceManager

Android进程间通信框架

背景： 为了应对移动应用内存限制的问题，移动应用通常进行多进程化(根据职责驱动原则和模式分解，分割业务到不同的进程中提高应用稳定性)，而多进程间通信的实现方式有多种方法，比如：aidl或定义自己binder通信接口进行通信(参考：[DroidIPC](https://github.com/devyok/DroidIPC) )。 ServiceManager是基于ContentProvider获取aidl接口的方式。

# 优势 #


- ServiceManager大大的降低了进程间的依赖，增强了灵活性，扩展性与可读性，同时提升了开发效率。


- ServiceManager为了简化开发人员的配置和降低错误，ServiceManager提供gradle插件来帮助开发人员在编译阶段完成配置。


# 安装 #
### 第一步 ###
在gradle文件引入ServiceManager插件

	buildscript {
	    dependencies {
	        classpath 'com.devyok.ipc:ipc-gradle-plugin:0.0.1'
	    }
	}

### 第二步 ###
在gradle文件中引入ipc-libcore
	
	
	dependencies {
	    classpath 'com.devyok.ipc:ipc-libcore:0.0.2'
	}
	
### 第二步 ###
在Application#onCreate中初始化ServiceManager

	ServiceManager.init(getApplicationContext());

在初始化之前你可以打开ServiceManager的调试开发

	LogControler.info("SampleApplication", "SampleApplication create");



# License #
ServiceManager is released under the [Apache 2.0 license](https://github.com/devyok/ServiceManager/blob/master/LICENSE).

Copyright (C) 2017 DengWei.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.