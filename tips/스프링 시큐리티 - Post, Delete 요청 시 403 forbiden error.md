
Spring Security 적용시키면,

Post, Delete 요청 시에 403 forbiden error 가 뜬다.

SecurityConfigure 에서  `csrf` 를 비활성화 해주면 된다.

**`csrf`**
Cross-site Request Forgery

사용자가 웹사이트에 로그인한 상태에서 사이트간 요청 위조 공격 코드가 삽입된 페이지를 열면, 공격 대상이 되는 웹사이트는 위조된 공격 명령이 믿을 수 있는 사용자로부터 발송된 것으로 판단하게 되어 공격에 노출된다.

&nbsp;


**securityConfig.class**

```java
@Configuration
public class SecurityConfig extends WebSecurityConfigurerAdapter {

    @Override
    protected void configure(HttpSecurity http) throws Exception {
        // @formatter:off
        http.csrf().disable();
        http.httpBasic();
        http.authorizeRequests()
                .antMatchers(HttpMethod.DELETE,"/api/categories/**").fullyAuthenticated()
                .antMatchers("/api/categories").permitAll()
                .anyRequest().permitAll();


        // @formatter:on
    }

}
```

시큐리티 환경설정에 `http.csrf().disable()` 을 해주면 에러는 사라진다.
