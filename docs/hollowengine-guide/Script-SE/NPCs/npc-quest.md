# Квесты

!!! info "Если нужно что-то сдать НПС, чтобы сюжет пошёл дальше"

    ```kotlin
    <npcID>.requestItems {
        // Здесь пишем то, что нужно сдать НПС
    }
    ```

## Принести предмет

!!! note "Принести определённый предмет"

    ```kotlin
        +item("<itemID>", <count>) // Принести [itemID] в количестве [count]
    ```
    
    - Обозначения: 
    > - `itemID` - Его можете получить, взяв нужный предмет в руки и прописав команду `/hollowengine hand` и после оно скопируется. 
    > - `count` - Кол-во предметов. 

---
