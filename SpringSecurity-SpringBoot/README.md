# spring-boot-security-3.0

Note : If you are using spring boot 3.1.x version then please do the below code change

    @Bean
    public SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {
        return http.csrf(AbstractHttpConfigurer::disable)
                .authorizeHttpRequests(auth ->
                        auth.requestMatchers("/product-service/welcome", "/product-service/addNewUser").permitAll()
                                .requestMatchers("/product-service/**")
                                .authenticated()
                )
                .httpBasic(Customizer.withDefaults()).build();
    }



docker run --name local-Vik-mysql -v myDbData:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=password -d -p 3306:3306 mysql:latest


[https://bcrypt-generator.com/](https://bcrypt-generator.com/) for encrypting password

INSERT INTO springData.UserInfo
(id, email, name, password, roles)
VALUES(1, 'vikram@gmail.com', 'Vikram', '$2a$12$Zv9a3QgsvjqXdCssxbMRV.7Joy.t26lGYlLqm.VWMBmB2morc2RnO', 'ADMIN');   //password = '$2a$12$Zv9a3QgsvjqXdCssxbMRV.7Joy.t26lGYlLqm.VWMBmB2morc2RnO'


Ref:-
[https://www.youtube.com/watch?v=R76S0tfv36w&t=2643s&ab_channel=JavaTechie](https://www.youtube.com/watch?v=R76S0tfv36w&t=2643s&ab_channel=JavaTechie)