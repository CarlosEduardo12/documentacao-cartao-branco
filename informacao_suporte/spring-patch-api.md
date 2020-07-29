# Como expor uma API PATCH no Spring?

Para expor uma API PATCH no Spring devemos utilizar a anotação [@PatchMapping](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/PatchMapping.html).

1º Precisamos criar um Controller com a anotação [@RestController](https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/bind/annotation/RestController.html).

```java
@RestController
public class meuController {
   // código omitido
}
```

2º Precisamos definir o recurso da nossa API utilizando a anotação [@RequestMapping](https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestMapping.html).


```java
@RestController
@RequestMapping("/v1/meu-recurso")
public class meuController {
   // código omitido
}
```

3º Precisamos criar nossa API de acordo com o objetivo e seu método HTTP.

```java
@RestController
@RequestMapping("/v1/meu-recurso")
public class meuController {

    @PatchMapping
    public ResponseEntity<?> minhaOperacao() {
        // código omitido
        return ResponseEntity.status(status).body(body);
    }

}
```

#Informação de Suporte

Quer saber mais sobre como criar API's REST no Spring? [Aqui você encontra como fazer isso !!!](https://spring.io/guides/gs/rest-service/)