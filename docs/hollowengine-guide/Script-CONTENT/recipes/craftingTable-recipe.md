# Верстак

!!! note "Рецепты крафтов на Верстаке"
	
	Вы можете создать свой собственный крафт на Верстаке.

---

!!! warning "Внимание"

	Всё что указывается в `[]` скобках, это тоже что и `<>`, то с условием что это - обязательное значение!

---

## Удалить рецепты

### По предмету результату

!!! info "Шаблон"
	
	```kts
	remuveByOutput("[<itemID_Output>]", <recipeType>, <checkTag>) // Удаляются все рецеты, на выходе которых получается [itemID]
	```

	> Обозначения:
	> - `itemID_Output` - Прежмет, получаемый на выходе(после крафта). Писать нужно именно `itemID`.
	>  - `itemID` - Уникальный `ID` предмета. У "Золотая морковь" -> `minecraft:golden_carrot`
	> - `recipeType` - Тип рецепта.
	> - `checkTag` - Проверка тега. Сравнивать ли тег двух предметов или только названия.

	Пример:

	```kts
	removeByOutput("minecraft:cobblestone") // Я удалил все рецепты крафта предмета "Булыжник"
	```

---

### По его ID

!!! info "Шаблон"

	```kts
	removeById("[<recipeID>]") // Удаляется конкретный [recipeID]
	```

	Пример:

	```kts
	removeById("minecraft:") // Я удалил рецепт 
	```

---

## Добавить рецепт

### По Json файлу

!!! info "\<invalid_name\=\"addByJson\"\>"

	```kts
	addFromJson(<newRecipeName>, <newRecipeData>) // Пока ничего неизвестно
	```

	\<invalid_description\=\"addByJson.desc\"\>

---

### Заменить рецепт

!!! info "Шаблон"

	```kts
	CraftingTable.replaceShaped("\[itemID_Output\]", <count>) {
		grid ( // Сетка крафта
			"\[\]\[\]\[\]",
			"\[\]\[\]\[\]";
			"\[\]\[\]\[\]" // [] - это слот в сетке
		)

		where {
			'\[<key>\]' = \[<itemID_Input>\]
			// И так, скоклько типо [key] указано в [grid] 
		}

		extra\["<inknown_1>"\] = "<inknown_2>" // Пока не знаю что это
	}
	```

	> Обозначения:
	> - `itemID_Output` - Предмет, получаемый на выходе(после крафта). Писать нужно именно `itemitemID`.
	>  - `itemID` - Уникальный `ID` предмета. У "Золотая морковь" -> `minecraft:golden_carrot`
	> - `count` - Кол-во предметов. Если на выходе  вы получаете 1, то можете неуказывать.
	> - `[]`:
	>  - Это слот, куда вы указываете ключ, чтобы потом по этому ключю ставить нужный предмет.
	>  - Если этот слот должет быть пустым, то ставить пробел.
	> - `key` - Ключ, который будет заменятся на указанный `itemID_Input` после.
	> - `itemID_Input` - То же самое что и `itemID_Output, но указывает входящий предмет(предмет, который будет использован в сетке крафта).

	Пример:

	```kts
	CraftingTable.replaceShaped(item("minecraft:bedrock"), 15) {
		grid(
			"!!@",
			"@!!",
			" % "
		)

		where{
			'!' - item("minecraft:dirt")
			'@' - tag("#minecraft:planks")
			'%' - tag("#minecraft:ores")
		}
	}
	```

---