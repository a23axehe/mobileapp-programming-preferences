
# Rapport
Uppgiftens första steg innebar att läsa datan från shared preferences i mainactivity. Detta gjordes genom koden:
TextView prefTextRef=new TextView(this);
prefTextRef=(TextView)findViewById(R.id.prefText);
prefTextRef.setText(myPreferenceRef.getString("MyAppPreferenceString", "No preference found."));
Koden fanns i canvas guiden och behövde inte anpassas så mycket efter koden eftersom inte mycket var skrivet än. 
Efter detta var det dags att skapa en second activity. Detta gjordes genom att gå in på github och återvinna den kod
som skrevs i uppgiften "screens". Efter att detta var klart var det dags att skriva samt spara preferences i den nya aktiviteten.
Detta gjordes genom att skapa en edittext samt en button. Genom edittexten gik det att skriva den preferens som önskades och sedan klicka
på save knappen. När save knappen klickades kördes funktionen savePref() som ser ut på följande sätt:
public void savePref(View v){
        // Get the text
        EditText newPrefText=new EditText(this);
        newPrefText=(EditText)findViewById(R.id.settingseditview);
        // Store the new preference
        myPreferenceEditor.putString("MyAppPreferenceString", newPrefText.getText().toString());
        myPreferenceEditor.apply();
        // Display the new preference
        TextView prefTextRef=new TextView(this);
        prefTextRef=(TextView)findViewById(R.id.prefText1);
        prefTextRef.setText(myPreferenceRef.getString("MyAppPreferenceString", "No preference found."));
        // Clear the EditText
        newPrefText.setText("");
    }
Vad som händer i denna funktion är att den först hämtar texten i edittexten och sparar den text till en variabel
som heter newPrefText. Efter att texten blivit sparad genom preferenceeditorn till "MyAppPreferenceString". Preferensen blir sedan sparad
genom den funktionen apply(). Efter att preferensen sparats så visas den i en textview nedanför save knappen. om "MyAppPreferenceString"
är tom printas meddelandet "No preference found".Det sista som händer är att edittexten rensas genom att sätta texten till tom. 
För att texten sedan ska visas i mainactivity lades kodsnutt som tidigare nämndes för att läsa preferensen i en metod som heter
onResume(). Detta gjordes för att när mainavtivity återupptas läses preferenserna in igen till skillnad from metoden 
onCreate() osm bara läste in preferenserna när aktiviteten skapades. 
När appen var klar såg de två vyerna ut på följande sätt:
![img.png](img.png)
![img_1.png](img_1.png)
