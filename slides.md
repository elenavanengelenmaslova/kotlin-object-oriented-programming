---
# try also 'default' to start simple
theme: default
background: dentist.jpeg
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: prism
canvasWidth: 800
# show line numbers in code blocks
lineNumbers: true

# persist drawings in exports and build
drawings:
  persist: false
# page transition
transition: slide-up
# use UnoCSS
css: unocss
---

# Object Oriented Programming with Kotlin and Spring Boot

Bite size kotlin session 4

<div class="pt-12">
    Elena van Engelen - Maslova
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/elenavanengelenmaslova/kotlin-fundamental-building-blocks" target="_blank" alt="GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: slide-up
---

## Format

Accelerate your programming skills by mastering the Object Oriented Programming while creating a Spring Boot REST API application for a Dental Clinic.️️

<v-clicks>

- 📘 **Master Object-Oriented Programming (OOP)** - Explore the fundamental elements of OOP in Kotlin.

- 💻 **Apply OOP Principles with Spring Boot** - Solidify your grasp of OOP by integrating its concepts into a 'Dentist Clinic' Spring Boot application.

- 🏁 **Craft a REST API** - Illuminate and test your application through a RESTful interface, leveraging Swagger and unit tests.

- 🎒 **Engaging Take-Home Assignments** - Undertake practical coding challenges to enhance your application's range and depth.

</v-clicks>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Here is another comment.
-->

---
layout: default
---

# Table of contents

<Toc minDepth="2" maxDepth="2"></Toc>


---
transition: slide-up
layout: section
level: 2
---

# Classes and objects, Data classes, Enum classes


---
transition: slide-up

level: 3
---

# Class relationships

### "Has-a" Relationships (Composition)
Example: A `Patient` class **has a** `DentalRecord`.

```plantuml
@startuml

class Patient {
  -DentalRecord record
}
class DentalRecord {
}
Patient --> DentalRecord : has-a

@enduml
```

---

### "Has-a" Relationships (Composition) types

<v-clicks>

- One-to-one: One instance relates to exactly one other instance.

- One-to-many: One instance relates to multiple other instances.

- Many-to-many: Multiple instances relate to multiple other instances.

- Bidirectional: Mutual association.

</v-clicks>

---

### "Is-a" Relationships (Inheritance)
Inheritance illustrates the "Is-a" relationship. In our Dental Clinic:
- A `Dentist` **is a** `DentalPractitioner`.
- A `Hygienist` **is a** `DentalPractitioner`.


```plantuml
@startuml
interface DentalPractitioner {
  +performTreatment(patient: Patient, treatment: Treatment): String
}

class Dentist {
}

class Hygienist {
}

Dentist -up-|> DentalPractitioner : implements
Hygienist -up-|> DentalPractitioner : implements
@enduml
```

---
transition: slide-up

level: 3
---
# Basic object model

```plantuml {scale: 1}
@startuml

left to right direction 

class Appointment 

class Dentist 

class Patient 

class DentalRecord 

class Treatment 

Appointment o-- Patient : Has
Appointment o-- Dentist : Has
Appointment o-- Treatment : Involves
Dentist -- Patient : Performs treatment on
Patient o-- DentalRecord : Has
DentalRecord o-- Treatment : Records

@enduml

```

```plantuml {scale: 1}
@startuml

class Clinic 
class Appointment 
class Dentist 
class Patient
class Treatment

Clinic "1" *-- "*" Appointment : has >
Clinic "1" *-- "*" Dentist : has >
Clinic "1" *-- "*" Patient : has >
Clinic "1" *-- "*" Treatment : has >
@enduml

```

---
transition: slide-up

level: 2
---
# Object keyword

---
transition: slide-up

level: 2
---
# Inheritance, Interfaces and Polymorphism

---
transition: slide-up

level: 2
---
# Generics

---
level: 2
---
# Generics

---
level: 2
---
# Sealed classes and Value classes

---
level: 2
---
# Smart casts and Destructuring declarations

---
level: 2
---
# Annotations

---
level: 2
---
# Conclusion 

---
layout: end
---

