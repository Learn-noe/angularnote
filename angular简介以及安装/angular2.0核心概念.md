## 一、组件
### 每个组件能完成各自的功能
### 生命周期钩子
	Constructor	构造器初始化
	OnChanges	第一次触发数据变化钩子
	Onlnit		组件初始化
	OnChanges	运行期间触发数据变化钩子
	OnDestroy	组件销毁前

### 组件示例
	@Component（{
		（选择器）selector:'hello',
		 (模板1)template:'<p>{{(数据绑定)greeting}}</p>',
			{
				数据绑定：
					属性绑定：<input [value]="mydata"/>
					事件绑定：<input (keyup)="handle($even)"/>
					双向绑定：<input [(ngModel)]="mydata" />
			}
		 (模板2)templateUrl:'path/to/hello.html'
	}）
	export class helloComponent{
		private greeting:string;
		constructor(){
		this.greeting='hello,angular2.0!';
		}
	}
### 二、指令
	指令{
		属性指令：改变组件模板的外观或者行为  如样式 等
		结构指令：改变组件模板的Dom结构，如ngif用来插入或者移除节点
	}
	
	组件（组件继承与指令） 自身带有模板的指令

	自定义指令 template:'<p highlight>{{greeting}}</p>',
		@Directive({
		    selector:'[highlight]'  //中括号表示指令作用在元素属性上
})
	export class HighlightDirective{
		constructor(el:ElementRef(内置对象),renderer(内置对象  辅助渲染):Renderer{
		renderer.setElementStyle(el.nativeElement,'backgroundColor','yellow')
		})
  	}
#### ElementRef    renderer  用于费浏览器解耦
## 三、服务
	服务是实现专一目的的逻辑单元
	    示例：
		export class LoggerService{
			constructor(){}
			 debug(msg:string){			
				console.log(msg)					
					}
			  error(msg:string){
				console.error(msg);
					}
					   }