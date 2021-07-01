# JavaClassConvert
 
```java
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        ArrayList<ModelTarget> data = convetModel1ToModel2();

        for (int i = 0; i < data.size(); i++) {
            Log.d(getClass().getSimpleName(), "onCreate: "+data.toString());
        }
    }

    private ArrayList<ModelTarget> convetModel1ToModel2() {
        ArrayList<ModelSource> listSource = new ArrayList<>();
        for (int i = 0; i < 10; i++) {
            listSource.add(new ModelSource(i, i+"_ModelSource"));
        }

        ArrayList<ModelTarget> listTarget = new ArrayList<>();
        for (int i = 0; i < listSource.size(); i++) {
            listTarget.add(new ModelTarget(listSource.get(i)));
        }

        listSource.clear();
        return listTarget;
    }
}

class ModelSource {

    public int id;
    public String name;

    public ModelSource() {}

    public ModelSource(int id, String name) {
        this.id = id;
        this.name = name;
    }
}

class ModelTarget extends ModelSource {

    public ModelTarget(ModelSource data) {
        this.id = data.id;
        this.name = data.name;
    }

    @Override
    public String toString() {
        return "ModelTarget{" +
                "id=" + id +
                ", name='" + name + '\'' +
                '}';
    }
}
```

---

```
Copyright 2021 M. Fadli Zein
```