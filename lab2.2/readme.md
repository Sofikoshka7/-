# Вторая практическая работа по ТМП

## Выполнила: Семёнова С.А. БИСО-03-20

Вариант 9
Информационная система технической экспертизы
Обзор: информационная система технической экспертизы позволяет соискателям грантов подавать заявки, независимым экспертам оценивать заявки, а держателям фонда принимать решение о выдаче гратов по результатам экспертизы заявок

```
@startuml
title Информационная  система технической экспертизы
skinparam backgroundcolor AntiqueWhite/Gold
participant соискатель
participant эксперт
participant держатель
participant заявка
participant решение

activate соискатель
activate заявка
соискатель -> заявка: подаёт заявку
deactivate заявка
activate решение
соискатель -> решение: ждёт решение
deactivate решение
deactivate соискатель
activate эксперт
activate заявка
эксперт -> заявка: оценивает заявку
deactivate заявка
activate держатель
эксперт -> держатель: уведомляет
deactivate эксперт
activate заявка
держатель -> заявка: смотрит на оценку эксперта
заявка -> держатель: получает оценку заявки
deactivate заявка
activate решение
держатель -> решение: выносит решение
deactivate держатель
activate соискатель
решение -> соискатель: решение принято
deactivate решение
deactivate соискатель
@enduml
```
![alt text](https://github.com/Sofikoshka7/TMP/blob/main/lab2.2/Screenshot_5.png)

```

```
![alt text](https://github.com/Sofikoshka7/TMP/blob/main/lab2.2/Screenshot_6.png)
