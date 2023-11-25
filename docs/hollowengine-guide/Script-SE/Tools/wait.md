# Продолжение скрипта

## По таймеру

!!! info "Ты можешь поставить ожидание после каждого действия, перед тем, как перейти к следующему"

	```jsx
	wait{ <time> }
	```

	- `time`: 
	> - `<num>` - в тиках. 
	> - `<num>.sec` - в секундах. 
	> - `<num>.min` - в минутах. 
	> - `<num>.hour` - в часах. 
	> --- 
	> Так же вы можете соединять их через `+`, пример: `10 + 20.sec + 3.min + 5.hour`. 

---

# По нажатию кнопки

!!! info "Скрипт будет ждать, пока не будет нажата указанная кнопка"

	```jsx
	keybind { Keybind.<key> }
	```
	
	- `key` - Кнопки на клавиатуре. [Узнать больше...](https://github.com/HollowHorizon/HollowEngine/blob/1.19.2/src/main/java/ru/hollowhorizon/hollowengine/common/util/Keybind.kt)

---