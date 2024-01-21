# Перемещение персонажа

Прежде всего персонаж может двигаться к разным целям:

![NPC движется до точки](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/.resourses/npc-moveToPos.gif)

## Блок

В качестве цели можно указать блок.

Если нужно чтобы персонаж пришёл к блоку и код продолжился, то пользуйтесь:
```kotlin
npc moveToPos { pos(x, y, z) }
```

Также есть вариант просто указать цель и персонаж будет стремиться туда всегда, пока ему не скажут остановиться:
```kotlin 
npc setMovingPos { pos(x, y, z) }
```

И соответственно, чтобы остановиться, просто укажите пустую цель:
```kotlin 
npc setMovingPos { null }
```

## Сущность / Моб

В качестве цели можно указать какого-нибудь моба, игрока, или например другого персонажа.

Если нужно чтобы персонаж пришёл к другому персонажу использовать фигурные скобки не следует:
```kotlin
npc1 moveToEntity npc2
```
А для моба соответственно стоит:
```kotlin
npc1 moveToEntity { entity }
```

Аналогично, можно указать и постоянную цель или `null`:
```kotlin 
npc1 setMovingEntity npc2 //персонаж

npc setMovingEntity { entity } //моб

npc setMovingEntity { null } //ничего
```

## Команда игроков

При этом методе будет выбран ближайший игрок команды и персонаж будет следовать за ним.

Соответственно для одноразового действия нужно писать:
```kotlin
npc1 moveToTeam { team }
```

А для постоянного следования:
```kotlin
npc setMovingTeam { team } //следовать

npc setMovingTeam { null } //перестать следовать
```

# Направление взгляда персонажа

Персонажу можно сказать смотреть на какой либо объект. Аналогично предыдущим случаям есть команды для постоянного вгляда или одиночной задачи.

![NPC смотрит в точку](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/.resourses/npc-lookAtPos.gif)

## Блок

Одноразовая задача:
```kotlin
npc lookAtPos { pos(x, y, z) }
```

Постоянная задача:
```kotlin
npc setLookingPos { pos(x, y, z) } //начать смотреть 

npc setLookingPos { null } //перестать смотреть 
```

## Сущность / Моб

Одноразовая задача:
```kotlin
npc1 lookAtEntity npc2 //для персонажей

npc lookAtEntity { entity } //для других сущностей
```

Постоянная задача:
```kotlin
npc1 setLookingEntity npc2 //начать смотреть на персонажа 

npc setLookingEntity { entity } //начать смотреть на моба

npc setLookingEntity { null } //перестать смотреть 
```

## Команда игроков

Одноразовая задача:
```kotlin
npc lookAtTeam { team }
```

Постоянная задача:
```kotlin
npc setLookingTeam { team } //начать смотреть 

npc setLookingTeam { null } //перестать смотреть 
```