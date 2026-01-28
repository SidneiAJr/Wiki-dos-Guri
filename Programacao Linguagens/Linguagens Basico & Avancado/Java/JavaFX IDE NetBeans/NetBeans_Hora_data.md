## ⏰ **4️⃣ Trabalhar com Datas e Horas no Java**

## 🎯 Objetivo
Aprender a manipular **datas e horas** utilizando as classes modernas do pacote `java.time`.

---

## 🧩 Obter a Data e Hora Atual
```java
import java.time.LocalDate;
import java.time.LocalTime;
import java.time.LocalDateTime;

LocalDate dataAtual = LocalDate.now();
LocalTime horaAtual = LocalTime.now();
LocalDateTime dataHoraAtual = LocalDateTime.now();

System.out.println("Data: " + dataAtual);
System.out.println("Hora: " + horaAtual);
System.out.println("Data e Hora: " + dataHoraAtual);
```

## 🧮 Formatar Datas
```java
import java.time.format.DateTimeFormatter;

DateTimeFormatter formato = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm:ss");
String formatada = dataHoraAtual.format(formato);
System.out.println("Formatada: " + formatada);
```
