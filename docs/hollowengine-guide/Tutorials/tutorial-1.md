# Туториал №1

!!! note "Мы спавним базового NPC, ожидаем 2 сек, говорим ему дойти до какой-то точки (позиции), затем посмотрит в сторону игрока, проходит 3 сек и исчезанет"
    ```kotlin
    val npc by NPCEntity.creating{
        world = "minecraft:overworld"
        pos = pos(0.5, -57.0, 0.5)
    }
    wait { 2.sec }
    
    npc moveToPos { pos(-10, -58, 6) }
    npc lookAtTeam { team }
    wait { 3.sec }
    
    npc.despawn()
    ```

---