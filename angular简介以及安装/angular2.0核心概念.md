## һ�����
### ÿ���������ɸ��ԵĹ���
### �������ڹ���
	Constructor	��������ʼ��
	OnChanges	��һ�δ������ݱ仯����
	Onlnit		�����ʼ��
	OnChanges	�����ڼ䴥�����ݱ仯����
	OnDestroy	�������ǰ

### ���ʾ��
	@Component��{
		��ѡ������selector:'hello',
		 (ģ��1)template:'<p>{{(���ݰ�)greeting}}</p>',
			{
				���ݰ󶨣�
					���԰󶨣�<input [value]="mydata"/>
					�¼��󶨣�<input (keyup)="handle($even)"/>
					˫��󶨣�<input [(ngModel)]="mydata" />
			}
		 (ģ��2)templateUrl:'path/to/hello.html'
	}��
	export class helloComponent{
		private greeting:string;
		constructor(){
		this.greeting='hello,angular2.0!';
		}
	}
### ����ָ��
	ָ��{
		����ָ��ı����ģ�����ۻ�����Ϊ  ����ʽ ��
		�ṹָ��ı����ģ���Dom�ṹ����ngif������������Ƴ��ڵ�
	}
	
	���������̳���ָ� �������ģ���ָ��

	�Զ���ָ�� template:'<p highlight>{{greeting}}</p>',
		@Directive({
		    selector:'[highlight]'  //�����ű�ʾָ��������Ԫ��������
})
	export class HighlightDirective{
		constructor(el:ElementRef(���ö���),renderer(���ö���  ������Ⱦ):Renderer{
		renderer.setElementStyle(el.nativeElement,'backgroundColor','yellow')
		})
  	}
#### ElementRef    renderer  ���ڷ����������
## ��������
	������ʵ��רһĿ�ĵ��߼���Ԫ
	    ʾ����
		export class LoggerService{
			constructor(){}
			 debug(msg:string){			
				console.log(msg)					
					}
			  error(msg:string){
				console.error(msg);
					}
					   }