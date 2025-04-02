# ChowApp1
##[Click here to access the GitHub repo] (https://github.com/ST10494793-Mpilenhle-Vilakazi/ChowApp)
## Video demonstration
https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fyoutube.com%2Fshorts%2FK3QQIzEye5o%3Fsi%3DMJXtyXsTxEzLiD5l&data=05%7C02%7Cst10494793%40vcconnect.edu.za%7C567b6593befa43a9901a08dd72286218%7Ce10c8f44f469448fbc0dd781288ff01b%7C0%7C0%7C638792239988787964%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=YBHrPnoQzOm9OFz0vmzINkDt7BzXBZa7%2B8MmwvVA7BI%3D&reserved=0
## About my app
  The **ChowApp** suggests meals based on the time of day entered by the user.

  ###Feactures:
  User enters time (0-23) and the app suggests a meal.
  Error handling ensures only valid time are accepted.
  Built using **Kotlin & Android Studio**.

  ##Design Considerations
  A **simple UI** with an EditText, Button, and TextView
  Ensured user-friendly input validation.
  Considered different meal options based on morning, afternoon, and evening

  ##Screenshots
  https://github.com/ST10494793-Mpilenhle-Vilakazi/ChowApp/blob/master/Screenshot%202025-04-02%20230604.png
  https://github.com/ST10494793-Mpilenhle-Vilakazi/ChowApp/blob/master/Screenshot_2025.04.02_23.05.04.602.png
  https://github.com/ST10494793-Mpilenhle-Vilakazi/ChowApp/blob/master/Screenshot_2025.04.02_23.05.17.027.png

// Code Attribution 
// This implementation of setOnClickListener was based on Android Developers' official documentation. 
// Link: https://developer.android.com/reference/android/widget/Button#setOnClickListener(android.view.View.OnClickListener)
// Author: Android Developers 
btnSuggestMeal.setOnClickListener {
    val hour = inputText.toIntOrNull()

    if (hour != null && hour in 0..23) {
        val suggestedMeal = suggestMeal(hour)
        txtMealSuggestion.text = "Suggested Meal: $suggestedMeal"
    } else {
        Toast.makeText(this, "Please enter a valid time (0-23)", Toast.LENGTH_SHORT).show()
    }
}

// Code Attribution 
// This Kotlin 'when' expression structure was adapted from the official Kotlin documentation. 
// Link: https://kotlinlang.org/docs/control-flow.html#when-expression 
// Author: JetBrains (Kotlin Team) 
private fun suggestMeal(hour: Int): String {
    return when (hour) {
        in 5..10 -> "Breakfast suggestion: Pancakes or Omelette"
        in 11..15 -> "Lunch suggestion: Sandwich or Salad"
        in 16..21 -> "Dinner suggestion: Pasta or Grilled Chicken"
        else -> "It's not a typical mealtime. How about a snack?"
    }
}

// Code Attribution 
// The use of toIntOrNull() for safe conversion was learned from the Kotlin Standard Library documentation. 
// Link: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/to-int-or-null.html
// Author: JetBrains (Kotlin Team) 
val hour = inputText.toIntOrNull()

// Code Attribution 
// The use of Toast messages for displaying errors was based on Android Developers documentation. 
// Link: https://developer.android.com/guide/topics/ui/notifiers/toasts
// Author: Android Developers 
Toast.makeText(this, "Please enter a valid time (0-23)", Toast.LENGTH_SHORT).show()
