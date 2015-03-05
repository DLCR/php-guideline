# PHP指导原则 #

## 0. meta ##

### 严重级别

- :bomb:禁止：禁止违反此类规则。我们认为此类规则无需很大努力便可以遵守，且能给我们带来足够大的好处。
- :warning:警告：通常不应违反此类规则。我们认为大多数情况下此类规则都应该被遵守。少数的例外情况在充分讨论后，加上注释说明情况。
- :cry:建议：建议尽量遵守此类规则。我们认为在充分理解此类规则的基础上，为了实际情况的其他好处而违反此类规则是可以接受的。或者规则本身并不具备明确的判断标准。

### 1. PSR

:warning: 除了1.x中说明的各种例外场景之下，必须遵守[PSR-1](http://www.php-fig.org/psr/psr-1/)、[PSR-2](http://www.php-fig.org/psr/psr-2/)、[PSR-4](http://www.php-fig.org/psr/psr-4/)的全部规则。

#### 1.1 单行字数

 :cry: 120的单行限制应当被遵守，涉及自动检查脚本可以将告警等级从PSR规定的warn降低到notice

### 2. 其他基础规定

#### 2.1 代码放置

:bomb: 禁止在一个文件中定义多个类  
:bomb: 禁止在PSR-4的目录范围内放置非类定义的php文件  
:bomb: 禁止在PSR-4的目录范围外放置类定义的php文件  

#### 2.2 php能力限制

:bomb: 禁止定义函数，使用静态工具类替代  
:bomb: 禁止使用全局变量  
:bomb: 禁止使用eval  
:bomb: 必须使用单入口模式，document root下只允许`index.php`一个php文件  
:bomb: 禁止使用`require_once`，`require`仅允许在上述index.php中使用。用PSR-4的loader加载代码文件  
:bomb: 禁止使用`include_once`  
:warning: `include`仅允许在模版实现内和模版文件内使用  

> :question: 模版定义不清

:warning: 不要使用任何形式的按引用传值  
:warning: 禁止使用`@`抑制错误

#### 2.3 php配置

:bomb: error_reporting设置E_ALL  

### 3.

:warning: 静态公开成员变量`public static $var`不允许修改  
:warning: 代表类型的整数、错误码、位掩码等必需定义类常量，杜绝magic number  
:cry: 同一种类的类常量应当具备共同的前缀  
:cry: 名字难以表达类常量的涵义时应当加上doc注释  


