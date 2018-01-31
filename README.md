# Calling-Database-Views-From-SpringDataJPA
###### Lets consider this view –
```
CREATE VIEW my_view AS
SELECT my_view_id, my_view_name FROM my_table;
```

##### We map this to a JPA object as –
```
@Entity
@Table(name = "my_view")
public class MyView implements Serializable {
private static final long serialVersionUID = 1L;
@Id
@Column(name = "my_view_id")
private Long myViewId;
@NotNull
@Column(name = "my_view_name")
private String myViewName;
}
```

###### We then create a repository –
```
@Autowired
private MyViewRepository myViewRepository;
// ...
long count = myViewRepository.count();
```
