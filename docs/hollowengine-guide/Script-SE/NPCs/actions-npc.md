# Действия для NPC

## Передвижение

### Positon

!!! note "NPC будет двигаться до этих координат | Шаблон"
	```kotlin
	<npcID> moveToPos { pos(x, y, z) }
	```


### Team

!!! note "NPC будет двигать до ближайшего игрока в команде | Шаблон"
	```kotlin
	<npcID> moveToTeam { team }
	```


### Any NPC

!!! note "NPC будет двигать до другого NPC | Шаблон"
	```kotlin
	<npcID> movdToEntity { <any_npcID> }
	```

![NPC движется до точки](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/hollowengine-guide/.resourses/npc-move.gif)

---

## Посмотреть

### Pos

!!! note "NPC посмотрит на указанные координаты | Шаблон"
	```kotlin
	<npcID> lookAtPos { pos(x, y, z) }
	```


### Team

!!! note "NPC посмотрит на ближайшего игрока в команде | Шаблон"
	```kotlin
	<npcID> lookAtTeam { team }
	```


### Any NPC

!!! note "NPC посмотрит на другого NPC | Шаблон"
	```kotlin
	<npcID> lookAtEntity { <any_npcID> }
	```


![NPC смотрить в точку](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/hollowengine-guide/.resourses/npc-look.gif)

---

# Сказать от лица NPC

!!! note "NPC скажет эти слова | Шалон"
	```kotlin
	<npcID> say { "<text>" }
	```

![NPC сказал "говно"](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/hollowengine-guide/.resourses/npc-say.gif)

---

## Действия с предметом

### Выкинуть предмет(бросить)

!!! note "Укажи NPC, какой предмет нужно выкинуть(бросить)"
	```kotlin
	<npcID> dropItem { item("<itemID>") } // На данный момент работает криво, кидает только на Юг. Ждём патча.
	```
	Предмет можно указать лёгким способом. Просто возьмите в основную руку нужный предмет и после пропишите команду `/hollowengine hand`, у вас скопируется данные о предмете вместе с `item`. Вам прсото нужно будет вставить это и всё.


### Взять предмет в руку

!!! info "`item("<itemID>")` можно получить через: `/hollowengine hand`"
	Просто возьмите в руку нужный предмет и пропишите эту команд, после она скопируется и вы можете вставить её туда, где нужно.

#### Способ №1

!!! note "Просто выкинуть ему предмет. Он подберёт его и возьмёт в правую руку"
	```kotlin
	// Ничего не требуется.
	```

![NPC взял предмет в руку-1](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/hollowengine-guide/.resourses/npc-give-item1.gif)


#### Способ №2

!!! note "Выдать ему определённый предмет в определённую руку через скрипт"
	```kotlin
	<npcID> giveLeftHand { item("<itemID>") } // Выдать предмет в левую руку
	// or
	<npcID> giveRightHand { item("<itemID>") } // Выдать предмет в правую руку
	```
	`item("<itemID>")` можно получить через: `/hollowengine hand`; Простосто возьмите в руку нужный предмет и пропишите эту команд, после она скопируется и вы можете вставить её туда, где нужно.


![NPC взял предмет в руку-2](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/hollowengine-guide/.resourses/npc-give-item2.gif)

---

## Взаимодействие с миром

### Использовать блок

!!! note "НПС сможет взаимодействовать с миром"
	```kotlin
	<npcID>.useBlock { pos(x, y, z) } // Взаимодействовать с блоком, который находится на координатах x, y, z
	```
	> `pos(x, y, z)` - Позиция блока, с которым нужно взаимодействовать. Принимает целые числа int.


---

# Атаковать цель

!!! note "Укажите кого атаковать"
	```kotlin
	<npcID>.setTarget{<type>}
	```
	> - `type` - `<any_npcID>`, team, <entity> (как именно работает оно - сам хз).

---
