# Spring Framework : 6.x / SpringBoot 3.2.x

- `LocalVariableTableParameterNameDiscoverer`는 Spring Framework 6.1, SpringBoot 3.2.x 버전에서 제거되었다.  
따라서 SpringFramework and Spring portfolio frameworks 내의 코드는 더 이상 바이트코드를 구문 분석하여 파라미터 이름을 추론하지 않는다.  
매개변수 이름에 dependency injection, property binding, SpEL expressions 또는 기타 사용 사례에 문제가 발생하면,  
`StandardReflectionParameterNameDiscoverer`와 호환되기 위해서는 파라미터 이름 유지를 위해 일반적인 Java 8+ -parameters flag를 사용하여 Java 소스를 컴파일해야 한다.  

- Kotlin 컴파일러를 사용하면 -java-parameter 플래그를 사용하는 것이 좋다.
  
</br>  

- 아래와 같은 코드를 사용하려면 IntelliJ IDEA에서 프로젝트 생성 후 설정해주면 된다.

```
@Slf4j
@RestController
public class HelloController {

    @GetMapping("/hello")
    public String hello(@RequestParam Integer data) {
        log.info("data = {}", data);

        return "ok";
    }

}
```  

<img width="840" alt="image" src="https://github.com/Hyeon-zero/Upgrading-to-Spring-Framework-6.x/assets/108206105/0f7cf667-35f8-430d-b20a-eef38f30ba64">  

</br>  

![image](https://github.com/Hyeon-zero/Upgrading-to-Spring-Framework-6.x/assets/108206105/50edd9cc-0a4c-4943-b767-9267728037e9)
