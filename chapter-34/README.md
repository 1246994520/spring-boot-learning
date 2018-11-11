## ǰ��
>��һ�½ڣ����������ʹ��`Spring-WS`����`WebService`������ʵ������`WebService`�ķ�ʽ�кܶ�ģ��������������ʹ��`apache cxf`������������`WebService`����

*   [ǰ��](#ǰ��)
*   [һ��֪ʶ](#һ��֪ʶ)
    *   [��ΪApache-CXF](#��ΪApache-CXF)
    *   [����JAX-WS�淶](#����JAX-WS�淶)
        *   [����ע�����](#����ע�����)
*   [SpringBoot����CXFʵ��](#SpringBoot����CXFʵ��)
    *   [����˹���](#����˹���)
    *   [�ͻ��˵���](#�ͻ��˵���)
        *   [�쳣����](#�쳣����)
    *   [�Զ���������](#�Զ���������)
        *   [�����������](#�����������)
        *   [�ͻ���������](#�ͻ���������)
*   [�ο�����](#�ο�����)
*   [�ܽ�](#�ܽ�)
*   [���](#���)
*   [������̸](#������̸)

## һ��֪ʶ
### ��ΪApache-CXF
>`Apache CXF`��һ����Դ��`Services`��ܣ�`CXF`����������`Frontend`��� API �������Ϳ���Services����`JAX-WS`��`JAX-RS`����Щ`Services`����֧�ֶ���Э�飬���磺`SOAP`��`XML/HTTP`��`RESTful HTTP `����`CORBA`�����ҿ����ڶ��ִ���Э�������У����磺`HTTP`��`JMS` ����`JBI`��**CXF������ Services �Ĵ�����ͬʱ��������Ȼ�غ�Spring�����޷켯��**��

�����ǹ��������Ľ��ܣ�https://github.com/apache/cxf

![](http://qiniu.xds123.cn/18-11-10/4837068.jpg)

��õ���ʹ��`cxf`����`web-service`�������ǻ���`JAX-WS`�淶��ʵ�ֵġ���Ȼ������`CXF`Ҳʵ����`JAX-RS`�淶��ʵ��`RESTFul Service`��

### ����JAX-WS�淶
>`JAX-WS`ȫ�ƣ�`Java API for XML-Based Web Services`��`JAX-WS`��һ�ֱ��ģ�ͣ���ͨ��֧�ֽ�����ע�͵ı�׼ģ�����ڿ���` Web Service `Ӧ�ó���Ϳͻ�������Ӧ�ó��򿪷���

`JAX-WS`��Java�����������һ����������Web�����API��
- �ڷ������ˣ��û�ֻ��Ҫͨ��`Java`���Զ���Զ�̵�������Ҫʵ�ֵĽӿ�`SEI��service endpoint interface��`�����ṩ��ص�ʵ�֣�ͨ������`JAX-WS`�ķ��񷢲��ӿھͿ��Խ��䷢��Ϊ`WebService`�ӿڡ�
- �ڿͻ��ˣ��û�����ͨ��`JAX-WS`��API����һ�������ñ��ض��������Զ�̵ķ�����ʵ�ֶ���Զ�̷������˵ĵ��á���Ȼ`JAX-WS`Ҳ�ṩ��һ����Եײ���Ϣ���в�����API���ã������ͨ��`Dispatch`ֱ��ʹ��SOAP��Ϣ��XML��Ϣ�����������ʹ��Provider����SOAP��XML��Ϣ��

#### ����ע�����
>`JAX-WS`�ṩ��һϵ�е�ע�⣬���Զ�`WebService`�Ľӿڹ淶�������½�������õļ���ע�⡣

- **@WebService**�����ڽ�Java����Ϊʵ��` Web Service `���߽�����˵�ӿ� (SEI) ���Ϊʵ��`Web Service`�ӿڡ�
������������У�
  - name�������Ե�ֵ����XML Web Service�����ơ���Ĭ������£���ֵ��ʵ��XML Web Service��������ƣ�**wsdl:portType **�����ơ�ȱʡֵΪ Java ���**������ + Service**�����ַ�����
  - targetNamespace��Ĭ�ϵ�ֵΪ "http://����/" ������ͨ���˱���ָ��һ���Զ����targetNamespaceֵ��
  - serviceName�����ⷢ���ķ�������ָ��` Web Service `�ķ������ƣ�wsdl:service��ȱʡֵΪ Java ��ļ����� + Service�����ַ�����
  - endpointInterface��
  - portName��**wsdl:portName**��ֵ��ȱʡֵΪ`WebService.name+Port`
  - wsdlLocation��ָ�����ڶ��� Web Service �� WSDL �ĵ��� Web ��ַ 
  
  
- **@WebMethod**����ʾ��Ϊһ��`Web Service`�����ķ�������֧����ʹ��`@WebService `ע�������ʹ��`@WebMethod`ע�⡣
  - **operationName**��ָ����˷�����ƥ���wsdl:operation �����ơ�ȱʡֵΪ Java ���������ơ����ַ�����
  - **action**������˲�������Ϊ������ SOAP �󶨣���ֵ��ȷ�� SOAPAction ͷ��ֵ��ȱʡֵΪ Java ���������ơ����ַ�����
  - **exclude**��ָ���Ƿ�� Web Service ���ų�ĳһ������ȱʡֵΪ false��������ֵ��
    
    
- **@WebParam**�����ڶ��ƴӵ���������`Web Service`��Ϣ������`XML`Ԫ�ص�ӳ�䡣

����ע�⣬���Բ鿴��[WebServiceע���ܽ�](https://blog.csdn.net/w410589502/article/details/51742004 "WebServiceע���ܽ�")

Ϊ���и�ֱ�۸��ܣ���ҿ��Կ����������wsdl�ļ�����Ӧ���ϸ�ע�����Ե�ֵ(����ǰ׺`oKong`)��

```java
//@WebService ����ʾ��
@WebService(targetNamespace = 'http://www.lqdev.cn/webservice' ,name = "oKongName", serviceName="oKongServiceName", portName = "oKongPortName",endpointInterface="cn.lqdev.learning.springboot.cxf.service.AuthorService")

//@webMethod @WebParam ��������ʾ��
@WebMethod(operationName="oKongOperationName",action="oKongAction")
String getAuthorName(@WebParam(name = "paramName") String name);
```
![](http://qiniu.xds123.cn/18-11-10/45706268.jpg)

��ǵ��е㻨���ѩn�ѡ��O����ҿ����Լ������¡�

## SpringBoot����CXFʵ��
>��������������һ���򵥵�ʾ������ʾ�£���η���������ν��з�����á�

### ����˹���
����һ�����̣�`spring-boot-cxf-service`.

0.����CXF��POM�ļ�
```xml
        <dependency>
            <groupId>org.apache.cxf</groupId>
            <artifactId>cxf-spring-boot-starter-jaxws</artifactId>
            <version>3.2.5</version>
        </dependency>
```
1.����ʵ�壬��`JAX-WS`�淶�������ӿڼ���ʵ���ࡣ
`AuthorDto.java`

```java
/**
 * ������Ϣʵ��
 * @author oKong
 *
 */
@Data
@Builder
@AllArgsConstructor
@NoArgsConstructor
public class AuthorDto {

    String name;
    
    List<String> hobby; 
    
    String birthday;
    
    String description;
    
    Sex sex;
}
```

`Sex.java`�Ա�ö����
```java
/**
 * �Ա�ö����
 * @author oKong
 *
 */
public enum Sex {

    MALE("male"),
    FEMALE("female");
    
    String value;
    
    Sex(String value) {
        this.value = value;
    }
    
    public String value() {
        return value;
    }

    public static Sex fromValue(String v) {
        for (Sex c : Sex.values()) {
            if (c.value.equals(v)) {
                return c;
            }
        }
        throw new IllegalArgumentException(v);
    }    
}
```
`AuthorService.java`�ӿ��� 

```java
/**
 * ��������ӿ�
 * @author oKong
 *
 */
@WebService(targetNamespace = WsConst.NAMESPACE_URI ,name = "authorPortType")
public interface AuthorService {

    /**
     * �������ƻ�ȡ������Ϣ
     * @author ���ߣ�oKong
     */
    @WebMethod(operationName="getAuthorByName")
    AuthorDto getAuthor(@WebParam(name = "authorName") String name);

    /**
     * ��ȡ�����б���Ϣ
     * @author oKong
     */
    @WebMethod
    List<AuthorDto> getAuthorList();
    
    /**
     * �����ַ�������
     * @author oKong
     */
    String getAuthorString(@WebParam(name = "authorName")String name);
}
```

`AuthorServiceImpl.java`�ӿ�ʵ����

```java
@WebService(
         targetNamespace = WsConst.NAMESPACE_URI, //wsdl�����ռ� 
         name = "authorPortType",                 //portType���� �ͻ������ɴ���ʱ Ϊ�ӿ�����
         serviceName = "authorService",           //����name����
         portName = "authorPortName",             //port����
         endpointInterface = "cn.lqdev.learning.springboot.cxf.service.AuthorService")//ָ������webservcie�Ľӿ��࣬����Ҳ��Ҫ����@WebServiceע��
public class AuthorServiceImpl implements AuthorService{

    @Override
    public AuthorDto getAuthor(String name) {
        AuthorDto author = new AuthorDto();
        author.setBirthday("1990-01-23");
        author.setName("������" + name);
        author.setSex(Sex.MALE);
        author.setHobby(Arrays.asList("��Ӱ","����"));
        author.setDescription("������һö�����Գ������ʱ�䣺" + new Date().getTime());
        return author;
    }

    @Override
    public List<AuthorDto> getAuthorList() {
        List<AuthorDto> resultList = new ArrayList<>();
        AuthorDto author = new AuthorDto();
        author.setBirthday("1990-01-23");
        author.setName("������oKong");
        author.setSex(Sex.MALE);
        author.setHobby(Arrays.asList("��Ӱ","����"));
        author.setDescription("������һö�����Գ������ʱ�䣺" + new Date().getTime());
        resultList.add(author);
        resultList.add(author);
        return resultList;
    }

    @Override
    public String getAuthorString(String name) {
        AuthorDto author = getAuthor(name);
        return author.toString();
    }
}
```
ע�⣺���ע����Բ鿴�½ڣ�[����ע�����](#����ע�����)

��Ҫ�ǽӿ�ʵ�����`@WebService`��Ӧ����ֵ��Ҫwsdl�ļ���ӳ���ϵ��
```java
@WebService(
         targetNamespace = WsConst.NAMESPACE_URI, //wsdl�����ռ� 
         name = "authorPortType",                 //portType���� �ͻ������ɴ���ʱ Ϊ�ӿ�����
         serviceName = "authorService",           //����name����
         portName = "authorPortName",             //port����
         endpointInterface = "cn.lqdev.learning.springboot.cxf.service.AuthorService")//ָ������webservcie�Ľӿ��࣬����Ҳ��Ҫ����@WebServiceע��

```
2.���������࣬�����࣬���÷���uri·���ȡ�

`WsConst.java`

```java
/**
 * ������
 * @author oKong
 *
 */
public class WsConst {
    public static final String NAMESPACE_URI = "http://www.lqdev.cn/webservice";
}
```
`CxfWebServiceConfig.java`

```java
/**
 * cxf������
 * @author oKong
 *
 */
@Configuration
public class CxfWebServiceConfig {
    
    //������Ҫע��  ����springmvc �ĺ����� ΪDispatcherServlet
    //�˴�������������bean�Ļ� ԭ����mvc�ͱ������ˡ��ɲ鿴�����ࣺDispatcherServletAutoConfiguration
    //һ�ַ������޸ķ������� ����ָ��bean���� 
    //������Ҫע�� ��beanName�������� cxfServletRegistration ʱ���ᴴ������CXFServlet�ġ�
    //����ɲ鿴���Զ������ࣺDeclaration org.apache.cxf.spring.boot.autoconfigure.CxfAutoConfiguration
    //Ҳ���Բ����ô�bean ֱ��ͨ�������� cxf.path ���޸ķ���·����
    @Bean("cxfServletRegistration")
    public ServletRegistrationBean dispatcherServlet() {
        //ע��servlet ����/ws ��ͷ������ ������ Ĭ��Ϊ��/services/*
        return new ServletRegistrationBean(new CXFServlet(), "/ws/*");
    }
    
    /**
     * ����ҵ������ ��ȻҲ����ֱ�� ��ʵ�����ϱ�ע @Service
     * @author oKong
     */
    @Bean
    public AuthorService authorService() {
        return new AuthorServiceImpl();
    }
    
    /*
     * �Ǳ�Ҫ��
     */
    @Bean(name = Bus.DEFAULT_BUS_ID)
    public SpringBus springBus() {
        SpringBus springBus = new SpringBus();
        return springBus;
    }
    
    /*
     * ����endpoint
     */
    @Bean
    public Endpoint endpoint(AuthorService authorService) {
        EndpointImpl endpoint = new EndpointImpl(springBus(), authorService);
        endpoint.publish("/author");//������ַ
        return endpoint;
    }
}
```
**ע�����**
- ����`ServletRegistrationBean`ʱ����Ҫע�����÷��������ƻ���bean������ʱ����Ҫ��Ĭ�ϵ�`DispatcherServlet`�������ˣ��ᵼ��ԭ�ȵ�`mvc`�ӿ��޷�ʹ�ã���Ϊ�������ˡ�
- �޸ķ��ʵ�·������ͨ������`ServletRegistrationBean`���޸ģ���ͬʱ��Ҫע����Ҫ����bean������Ϊ`cxfServletRegistration`����Ȼ�����ע����`CXFServlet`�ġ�����ԭ��ɲ鿴�Զ������ࣺ`org.apache.cxf.spring.boot.autoconfigure.CxfAutoConfiguration`��

![CxfAutoConfiguration](http://qiniu.xds123.cn/18-11-10/16808447.jpg)

���ԣ�**�޸ķ���·��������ͨ�������`cxf.path`�����á���Ĭ�ϵķ���urlΪ��`/services`**

3.���������࣬ͬʱ����Ӧ�á�
```java
/**
 * cxf���񷢲�ʾ��
 * @author oKong
 *
 */
@SpringBootApplication
@Slf4j
public class CxfServiceApplication {

    public static void main(String[] args) throws Exception {
        SpringApplication.run(CxfServiceApplication.class, args);
        log.info("spirng-boot-cxf-service-chapter34����!");
    }
}
```
�����󣬿��Դӿ���̨�������Է��ʵ�url·����Ϣ��
```
2018-11-10 22:06:40.898  INFO 46364 --- [ost-startStop-1] o.s.b.w.servlet.ServletRegistrationBean  : Mapping servlet: 'CXFServlet' to [/ws/*]
2018-11-10 22:06:40.899  INFO 46364 --- [ost-startStop-1] o.s.b.w.servlet.ServletRegistrationBean  : Mapping servlet: 'dispatcherServlet' to [/]
```

���ʣ�http://127.0.0.1:8080/ws/author?wsdl ����֤�Ƿ񷢲��ɹ���

![author](http://qiniu.xds123.cn/18-11-10/79105494.jpg)

�Դˣ�`webService`�����ɹ��ˡ�

### �ͻ��˵���
����һ���ͻ��˹��̣�`spring-boot-cxf-client`��

0.����cxf������
```xml
        <dependency>
            <groupId>org.apache.cxf</groupId>
            <artifactId>cxf-spring-boot-starter-jaxws</artifactId>
            <version>3.2.5</version>
        </dependency> 
```
1.����`wsdl`�ļ���ͬʱ���ò����`cxf-codegen-plugin`��������ࡣ
```xml
<!-- cxf-codegen-plugin -->
      <plugin>
        <groupId>org.apache.cxf</groupId>
        <artifactId>cxf-codegen-plugin</artifactId>
        <version>3.2.5</version>
        <executions>
          <execution>
            <id>generate-sources</id>
            <phase>generate-sources</phase>
            <configuration>
              <sourceRoot>${project.build.directory}/generated/cxf</sourceRoot>
              <wsdlOptions>
                <wsdlOption>
                  <wsdl>src/main/resources/wsdl/author.wsdl</wsdl>
                  <wsdlLocation>classpath:wsdl/author.wsdl</wsdlLocation>
                </wsdlOption>
              </wsdlOptions>
            </configuration>
            <goals>
              <goal>wsdl2java</goal>
            </goals>
          </execution>
        </executions>
      </plugin>
```

**��`wsdl`�ļ�������`main/resources/wsdl`Ŀ¼�¡�֮��ִ�У�`mvn generate-sources`����ͻ��Զ�������Ӧ�����ļ��ˡ�������Ӧ�����ļ���`src/java`Ŀ¼�¼��ɡ�����ֱ��ָ��`sourceRoot`Ҳ�ǿ��Եġ�**

![](http://qiniu.xds123.cn/18-11-10/92599225.jpg)

2.�������õ������࣬������ʾ���ַ�ʽ��

`WsConst.java`

```java
/**
 * ������
 * @author oKong
 *
 */
public class WsConst {
    public static final String NAMESPACE_URI = "http://www.lqdev.cn/webservice";
    public static final String SERVICE_ADDRESS= "http://127.0.0.1:8080/ws/author?wsdl";
}
```

`CxfClinetConfig.java`

```java
/**
 * ������
 * 
 * @author oKong
 *
 */
@Configuration
public class CxfClientConfig {

    
    /**
     *  �Խӿڴ���ʽ���е��� AuthorPortType�ӿ�
     */
    @Bean("cxfProxy")
    public AuthorPortType createAuthorPortTypeProxy() {
        JaxWsProxyFactoryBean jaxWsProxyFactoryBean = new JaxWsProxyFactoryBean();
        jaxWsProxyFactoryBean.setServiceClass(AuthorPortType.class);
        jaxWsProxyFactoryBean.setAddress(WsConst.SERVICE_ADDRESS);//�����ַ��http://127.0.0.1:8080/ws/autho

        return (AuthorPortType) jaxWsProxyFactoryBean.create();
    }
    
    /*
     * ���ö�̬������ʽ ����Ҫָ������ӿ�
     */
    @Bean
    public Client createDynamicClient() {
        JaxWsDynamicClientFactory dcf = JaxWsDynamicClientFactory.newInstance();
        Client client = dcf.createClient(WsConst.SERVICE_ADDRESS);
        return client;
    } 
}
```
ע�⣺����ʹ��`JaxWsProxyFactoryBean`��`JaxWsDynamicClientFactory`�����⣬������ֱ��ʹ���Զ����ɵ�`AuthorService`��ֱ�ӵ��õģ�����̳���`javax.xml.ws.Service`��
�磺
```java
    /*
     * ֱ�ӵ���
     */
    @Bean("jdkProxy")
    public AuthorPortType createJdkService() {
        AuthorService authorService = new AuthorService();
        return authorService.getAuthorPortName();
    }
```
��ʵ�������ʹ��`AuthorPortType`���е��õġ�

3.�������Ʋ㣬���е���ʾ����
```java
/**
 * ����ʾ��
 * @author oKong
 *
 */
@RestController
@RequestMapping("/cxf")
public class DemoController {

    @Autowired
    Client client;
    
    @Autowired
    @Qualifier("cxfProxy")
    AuthorPortType authorPort;
    
    @GetMapping("/getauthorstring")
    public String getAuthorString(String authorName) {
        return authorPort.getAuthorString(authorName);
    }
    
    @GetMapping("/getauthor")
    public AuthorDto getAuthor(String authorName) {
        return authorPort.getAuthorByName(authorName);
    }
    
    @GetMapping("/getauthorlist")
    public List<AuthorDto> getAuthorList() {
        return authorPort.getAuthorList();
    }
    
    @GetMapping("/dynamic/{operation}")
    public Object getAuthorStringByDynamic(@PathVariable("operation")String operationName, String authorName) throws Exception {
        //����ͼ򵥵��ж��� 
        Object[] objects = null; 
//        client.getEndpoint().getBinding().getBindingInfo().getOperations()
        if ("getAuthorList".equalsIgnoreCase(operationName)) {
            objects = client.invoke(operationName);
        } else if ("getAuthorString".equalsIgnoreCase(operationName)) {
            objects = client.invoke(operationName, authorName);
        } else if ("getAuthorByName".equalsIgnoreCase(operationName)) {
            objects = client.invoke(operationName, authorName);
        } else {
            throw new RuntimeException("��Ч�ĵ��÷���");
        }
        return objects != null && objects.length > 0 ? objects[0] : "�����쳣";
    }    
}
```

4.��д�����࣬ͬʱ�ƶ�Ӧ�ö˿�Ϊ��8090��
```java
/**
 * cxf-�ͻ��˵���ʾ��
 * 
 * @author oKong
 *
 */
@SpringBootApplication
@Slf4j
public class CxfClientApplication {

    public static void main(String[] args) throws Exception {
        SpringApplication.run(CxfClientApplication.class, args);
        log.info("spring-boot-cxf-client-chapter34����!");
    }
}
```

�˿ں����ã�
```
server.port=8090
```

5.����Ӧ�ã����η��ʡ��鿴�Ƿ���óɹ���

http://127.0.0.1:8090/cxf/getauthorstring?authorName=oKong

![](http://qiniu.xds123.cn/18-11-11/23849909.jpg)

http://127.0.0.1:8090/cxf//getauthorlist?authorName=oKong

![](http://qiniu.xds123.cn/18-11-10/59069735.jpg)

��̬������ʽ���ã�
http://127.0.0.1:8090/cxf/dynamic/getAuthorList?authorName=oKong
![](http://qiniu.xds123.cn/18-11-10/30214354.jpg)

�����ľͲ�һһ��ͼ�ˣ������з����¡�

#### �쳣����
`Cxf`�����쳣ʱ����ͳһ�׳���`org.apache.cxf.interceptor.Fault`��ģ�������Ҫ�����쳣��������ͳһ�쳣������в��񣬹���ͳһ�쳣�������Բ鿴���£�[�ڰ��£�ͳһ�쳣������У�鴦��](http://blog.lqdev.cn/2018/07/20/springboot/chapter-eight/ "�ڰ��£�ͳһ�쳣������У�鴦��")��

### �Զ���������
CXF����������Ϊ���֣�`InInterceptor`��`OutInterceptor`���Զ��׼���`InInterceptor`���Դ���**soap������Ϣ**��`OutInterceptor`���Դ���**soap��Ӧ��Ϣ**�������������̳���`AbstractPhaseInterceptor<Message>`�ӿ��࣬���ң�����Ҳ�Դ��˺ܶ��������������������ӿ�����������־������֮��ģ�`LoggingInInterceptor`��`LoggingOutInterceptor`��

![](http://qiniu.xds123.cn/18-11-10/22071800.jpg)

��������ͼ��

![](http://qiniu.xds123.cn/18-11-10/67882812.jpg)

���������Ľ׶Σ�

 **������������**�����¼����׶Σ���Щ�׶ΰ��������������е��Ⱥ�˳�����С�
 
![](http://qiniu.xds123.cn/18-11-10/52675801.jpg)

**�����������**�����¼����׶Σ���Щ�׶ΰ��������������е��Ⱥ�˳�����С�

![](http://qiniu.xds123.cn/18-11-10/94131373.jpg)

�������ƣ��ɲ鿴��`org.apache.cxf.phase.Phase`��

![](http://qiniu.xds123.cn/18-11-10/17838454.jpg)

���ڣ������Զ����ʵ����������ʵ������ʱheader��Ҫ�����ض����������ߴ�ҿɲ�дһЩ��ȫУ����Զ���������������ֻ�Ǽ򵥵�ʾ����
#### �����������
1.������������`CheckAuthInterceptor.java`

```java
/**
 * ����-��ȫУ��������
 * 
 * @author oKong
 *
 */
@Slf4j
public class CheckAuthInterceptor extends AbstractPhaseInterceptor<SoapMessage> {

    public CheckAuthInterceptor() {
        super(Phase.PRE_INVOKE);// ���ؽڵ㣺����֮ǰ
    }

    @Override
    public void handleMessage(SoapMessage message) throws Fault {
        log.info("������������ʼ���飺{}", message);
        // ������
        List<Header> headers = message.getHeaders();

        // �ж��Ƿ��header
        // ���headers�Ƿ����
        if (headers == null | headers.size() < 1) {
            throw new Fault(new IllegalArgumentException("��֤ʧ�ܣ��봫����ȷ����(40001)"));//���Զ������淶
        }
        //ȡ��header
        Header header = headers.get(0);
        //��ȡ����
        Element element = (Element) header.getObject();//�����ȡ�ľ�ʱ auth������
        NodeList tokenNode = element.getElementsByTagName("token");
        if(tokenNode == null || tokenNode.getLength() < 1) {
            //��token�ڵ�
            throw new Fault(new IllegalArgumentException("��֤ʧ�ܣ��봫����ȷ����(40002)"));//�Զ������淶
        }
        //��ȡtoken
        String token = tokenNode.item(0).getTextContent();
        log.info("�����tokenΪ��{}", token);
        //������Զ�token ��Ч�Խ����ж�
    }
}
```
2.Endpoint�м������������á�
```java
    /*
     * ����endpoint
     */
    @Bean
    public Endpoint endpoint(AuthorService authorService) {
        EndpointImpl endpoint = new EndpointImpl(springBus(), authorService);
        endpoint.publish("/author");//������ַ
        endpoint.getInInterceptors().add(createCheckAuthInterceptor());//����������
//        endpoint.getOutInterceptors().add()//��Ӧ������
        return endpoint;
    }
    
    @Bean
    public Interceptor<SoapMessage> createCheckAuthInterceptor(){
        return new CheckAuthInterceptor();
    }
```

#### �ͻ���������

1.��д��������

```java
/**
 * ����-��ȫУ��������
 * @author oKong
 *
 */
public class AuthInterceptor extends AbstractPhaseInterceptor<SoapMessage>{
    
    public AuthInterceptor() {
        super(Phase.PREPARE_SEND);//׼������ʱ��������
    }

    @Override
    public void handleMessage(SoapMessage message) throws Fault {
        //������
        List<Header> headers = message.getHeaders();
        
        Document doc = DOMUtils.createDocument();
        Element element = doc.createElement("auth");
        Element tokenEle = doc.createElement("token");
        tokenEle.setTextContent(UUID.randomUUID().toString());
        element.appendChild(tokenEle);
        //������Ҫע�� Ĭ������� ��ʹ�� org.w3c.dom.Element�������ö���ֵ�ġ�
        //Ҳ����ָ�� DataBinding ���ö���ġ��ɼ̳г����ࣺ org.apache.cxf.databinding.AbstractDataBinding
        //����Դ��ɲ鿴:org.apache.cxf.binding.soap.interceptor.SoapOutInterceptor
        Header tokenHeader = new SoapHeader(new QName(""), element);
//        tokenHeader.setDataBinding()
        headers.add(tokenHeader);
    }

}
```
**������Ҫע�⣺**
- ����headerʱ��Ĭ����`org.w3c.dom.Element`����
- �Զ������ʱ��������`DataBinding`����������δ���ԣ�ֻ�ǿ���һ��Դ�룬�����д��߼�������Ȥ��ͬѧ�����������ԣ���

2.�������м�����������
`CxfClientConfig.java`

```java
    /**
     *  �Խӿڴ���ʽ���е��� AuthorPortType�ӿ�
     */
    @Bean("cxfProxy")
    public AuthorPortType createAuthorPortTypeProxy() {
        JaxWsProxyFactoryBean jaxWsProxyFactoryBean = new JaxWsProxyFactoryBean();
        jaxWsProxyFactoryBean.setServiceClass(AuthorPortType.class);
        jaxWsProxyFactoryBean.setAddress(WsConst.SERVICE_ADDRESS);//�����ַ��http://127.0.0.1:8080/ws/autho
        jaxWsProxyFactoryBean.getOutInterceptors().add(createInterceptor());//�����Զ���������
        return (AuthorPortType) jaxWsProxyFactoryBean.create();
    }
    
    /*
     * ���ö�̬������ʽ ����Ҫָ������ӿ�
     */
    @Bean
    public Client createDynamicClient() {
        JaxWsDynamicClientFactory dcf = JaxWsDynamicClientFactory.newInstance();
        Client client = dcf.createClient(WsConst.SERVICE_ADDRESS);
        client.getOutInterceptors().add(createInterceptor());
        return client;
    }
    
    @Bean
    public Interceptor<SoapMessage> createInterceptor() {
        return new AuthInterceptor();
    }
```

�����������ٴ�����Ϳ��Կ��������־����ˣ��������Ų�����token�����������ء�

![��������](http://qiniu.xds123.cn/18-11-10/43308435.jpg)

�쳣����

![�쳣����](http://qiniu.xds123.cn/18-11-10/54892013.jpg)

## �ο�����
1. [http://cxf.apache.org/docs/springboot.html](http://cxf.apache.org/docs/springboot.html "http://cxf.apache.org/docs/springboot.html")

2. [https://www.code996.cn/post/2017/cxf-interceptor/](https://www.code996.cn/post/2017/cxf-interceptor/ "https://www.code996.cn/post/2017/cxf-interceptor/")
## �ܽ�
>���½���Ҫ�򵥽�����`apache-cxf`��ʹ�á�������ʾ��д�������ҷ��ֱ�`spring-ws`����ѽ��Ҳ������������⡢�߼��Ƚ�����������Ҳ������һЩ���컯�Ķ�������֪���ǲ�����Ķ�`spring-ws`�˽�Ĳ���ѽ��û�з���`spring-ws`���ŵ�ѽ���Դˣ�����`WebService`�����¾���ʱ��һ�����ˡ�

## ���
>Ŀǰ�������Ϻܶ���ж���`SpringBoot`ϵ�н̳̣�������ͬ����������ˡ�**ԭ�����ף����ֲ���**����ϣ����Ҷ��֧�֡���������������֮�������������лл��

## ������̸
- ����QQ��`499452441`
- ΢�Ź��ںţ�`lqdevOps`

![���ں�](http://qiniu.xds123.cn/default/wxgzh8cm.jpg)

���˲��ͣ�[http://blog.lqdev.cn](http://blog.lqdev.cn "http://blog.lqdev.cn")

����ʾ����[https://github.com/xie19900123/spring-boot-learning/tree/master/chapter-34](https://github.com/xie19900123/spring-boot-learning/tree/master/chapter-34 "https://github.com/xie19900123/spring-boot-learning/tree/master/chapter-34")

ԭ�ĵ�ַ��[http://blog.lqdev.cn/2018/11/11/springboot/chapter-thirty-four/](http://blog.lqdev.cn/2018/11/11/springboot/chapter-thirty-four/)