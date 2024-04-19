
# Rapport

En andra aktivitet initierades och döptes till MainActivity2 och fick tillhörande XML-fil activity_main.xml.
[MainActivity2.java](app/src/main/java/com/example/screens/MainActivity2.java)
[activity_main.xml](app/src/main/res/layout/activity_main2.xml)

En knapp med ID:t myButton lades till på första sidan (activity_main.xml).
Den stylades och placerades i mitten av skärmen.
```
    <Button
        android:id="@+id/myButton"
        android:text="@string/click_text"
        android:layout_width="300dp"
        android:background="@color/colorAccent"
        android:textSize="18sp"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.499" />
```

Knappen kopplas via "findViewById" ihop med en funktion som tar en till den andra sidan, alltså MainActivity2, när man klickar på den.
```
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button b = findViewById(R.id.myButton);

        b.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent intent = new Intent(MainActivity.this, MainActivity2.class);
                startActivity(intent);
            }
        });
    }
```
En ImageView läggs till i den activity_main2.xml
Den placeras i mitten av skärmen.
```
  <ImageView
      android:id="@+id/imageView3"
      android:layout_width="300dp"
      android:layout_height="300dp"
      android:contentDescription="black cat"
      app:layout_constraintBottom_toBottomOf="parent"
      app:layout_constraintEnd_toEndOf="parent"
      app:layout_constraintStart_toStartOf="parent"
      app:layout_constraintTop_toTopOf="parent"
      app:srcCompat="@drawable/cat" />
```
Bilden är en drawable som också läggs till. Den skapades i Adobe Illustrator.
[Drawable Cat](app/src/main/res/drawable/cat.png)

En TextView läggs till i activity_main2.xml.
Den styleas och placeras ovanför ImageView i förhållande till den.
```
<TextView
      android:layout_width="match_parent"
      android:layout_height="wrap_content"
      android:text="Yay, it worked!"
      android:textAlignment="center"
      android:textColor="@color/colorPrimary"
      android:textSize="40sp"
      app:layout_constraintBottom_toTopOf="@+id/imageView3"
      app:layout_constraintEnd_toEndOf="parent"
      app:layout_constraintStart_toStartOf="parent"
      app:layout_constraintTop_toTopOf="parent" />
```

