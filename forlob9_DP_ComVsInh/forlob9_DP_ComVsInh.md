***Helt nye programmerings-keywords:*** interface, implements        
***Nye termer:*** design pattern, anonym klasse        
***Vigtige termer ( i allerede kender ):*** komposition, nedarvning       

[https://processing.org/reference/implements.html](https://processing.org/reference/implements.html)            
[https://www.baeldung.com/java-anonymous-classes](https://www.baeldung.com/java-anonymous-classes)

------------------------------------------------

# Design Patterns - composition vs. inheritance

Vi har nu prøvet kræfter med at lave et objektorienteret bibliotek - og set fordelene ved at opdele forskellige elementer i klasser så de kan genbruges af andre.

Men objektorienteret programmering kan selvfølgelig både anvendes på hensigsmæssige og mindre hensigtsmæssige måder!     
Nogle problemstillinger går igen i mange forskellige programmer og derfor er der gennem tiden opstået hensigtsmæssige oop-design-principper og oop-arkitekturer til at løse disse problemer.

## Design princip - Vælg komposition istedet for nedarvning!

Dette er et meget vigtigt princip indenfor OOP. Du kan læse om det her:

[https://www.geeksforgeeks.org/favoring-composition-over-inheritance-in-java-with-examples/](https://www.geeksforgeeks.org/favoring-composition-over-inheritance-in-java-with-examples/)

## Design Pattern - Strategy Pattern

Et design pattern er en objektorienteret arkitektur, der løser en bestemt type problemstilling.   
Vi kigger her på en "Strategy Pattern" der direkte udnytter "komposition istedet for nedarvning":

[StrategyPatternHeadFirst.pdf](StrategyPatternHeadFirst.pdf)

[https://refactoring.guru/design-patterns/strategy](https://refactoring.guru/design-patterns/strategy)

## Logbogs opgaven (opgavebesvarelsen skal indskrives i din logbog!)
Udtænk en knap klasse, der anvender "strategy pattern", således den handling som udføres skal pakkes ind i en såkaldt "strategy".
- Tegn klassediagrammet og skriv nedenunder, hvilke roller dine klasser har sammenlignet med "refactoring.guru".
- Udarbejd et lille program, der anvender din knap.


Her et eksempel på hvordan klient-koden kunne se ud:
```java
int result = 0;
Button b1;
void setup() {
  size(500, 500);
  b1 = new Button(10, 10, 80, 30, "+1", new Action() {
    public void execute() {result = result+1;}
  });
}

  void draw() {
    clear();
    b1.display();
    fill(255);
    textSize(20);
    text(result,width/2,height/2);
  }

  void mousePressed() {
    b1.click();
  }

  void mouseReleased() {
    b1.release();
  }
```
