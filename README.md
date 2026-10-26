# session-5
### Task 1: IPL Fan Bot (`if-else-if` Ladder)

```c
#include <stdio.h>
#include <string.h>

int main() {
    char team[50];

    printf("Enter your favorite IPL team (e.g., MI, CSK, RCB, KKR): ");
    scanf("%s", team);

    if (strcmp(team, "MI") == 0 || strcmp(team, "Mumbai Indians") == 0) {
        printf("Duniya Hila Denge Hum! Go Mumbai Indians!\n");
    } else if (strcmp(team, "CSK") == 0 || strcmp(team, "Chennai Super Kings") == 0) {
        printf("Whistle Podu! Chennai Super Kings for the win!\n");
    } else if (strcmp(team, "RCB") == 0 || strcmp(team, "Royal Challengers Bengaluru") == 0) {
        printf("Ee Sala Cup Namde! Royal Challengers Bengaluru all the way!\n");
    } else if (strcmp(team, "KKR") == 0 || strcmp(team, "Kolkata Knight Riders") == 0) {
        printf("Korbo Lorbo Jeetbo Re! Go KKR!\n");
    } else {
        printf("Team not found!\n");
    }

    return 0;
}

```

---

### Task 2: Zomato Meal Suggestion Tool (`switch-case`)

In C, `switch` works directly with integers or characters. A clean standard approach maps the meal type using a single character code (or an integer option):

```c
#include <stdio.h>

int main() {
    int choice;

    printf("Select meal time:\n");
    printf("1. Breakfast\n2. Lunch\n3. Snack\n4. Dinner\n");
    printf("Enter your choice (1-4): ");
    scanf("%d", &choice);

    switch (choice) {
        case 1:
            printf("Suggestion: Idli Sambar with hot Filter Coffee!\n");
            break;
        case 2:
            printf("Suggestion: Paneer Butter Masala with Butter Naan & Jeera Rice!\n");
            break;
        case 3:
            printf("Suggestion: Samosa with Masala Chai!\n");
            break;
        case 4:
            printf("Suggestion: Dal Tadka with Tandoori Roti!\n");
            break;
        default:
            printf("Try some fruits!\n");
            break;
    }

    return 0;
}

```

---

### Task 3: Flipkart Discount Calculator (`nested if`)

```c
#include <stdio.h>

int main() {
    float cartAmount, discount = 0.0f, finalAmount;

    printf("Enter total cart amount: ₹");
    scanf("%f", &cartAmount);

    // Using nested if statements to evaluate discount slabs
    if (cartAmount > 1000) {
        if (cartAmount > 2000) {
            discount = 0.20f * cartAmount; // 20% discount
            printf("Discount Applied: 20%% (₹%.2f)\n", discount);
        } else {
            discount = 0.10f * cartAmount; // 10% discount
            printf("Discount Applied: 10%% (₹%.2f)\n", discount);
        }
    } else {
        discount = 0.0f; // No discount
        printf("No discount applied (Cart under ₹1000).\n");
    }

    finalAmount = cartAmount - discount;
    printf("Final amount to pay: ₹%.2f\n", finalAmount);

    return 0;
}

```

---

### Task 4: Multi-Tier Age Eligibility Checker

To print **all** applicable messages for a given age (cumulative milestones), each milestone is checked sequentially:

```c
#include <stdio.h>

int main() {
    int age;

    printf("Enter your age: ");
    scanf("%d", &age);

    if (age >= 18) {
        printf("Eligible for Driving License\n");
        
        if (age >= 21) {
            printf("Eligible for Credit Card\n");
        }
        
        if (age >= 25) {
            printf("Eligible for Car Rental\n");
        }
    } else {
        printf("Not eligible for Driving License, Credit Card, or Car Rental yet.\n");
    }

    return 0;
}

