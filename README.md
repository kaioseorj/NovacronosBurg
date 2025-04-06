Aqui estão três scripts para Bloxburg:

*Script 1: Auto-Farmar Dinheiro*

```
local player = game.Players.LocalPlayer
local character = player.Character

while true do
    for _, workstation in pairs(game.Workspace.Environment.Locations.BloxyBurgers.CashierWorkstations:GetChildren()) do
        if workstation.Occupied.Value then
            local customer = workstation.Occupied.Value
            local order = customer.Order
            local burger = order.Burger.Value
            local fries = order.Fries.Value
            local cola = order.Cola.Value

            if burger then
                game.ReplicatedStorage.BurgerEvent:FireServer(workstation, burger)
            end

            if fries then
                game.ReplicatedStorage.FriesEvent:FireServer(workstation, fries)
            end

            if cola then
                game.ReplicatedStorage.ColaEvent:FireServer(workstation, cola)
            end
        end
    end
    wait(1)
end
```

*Script 2: Auto-Entregar Comida*

```
local player = game.Players.LocalPlayer
local character = player.Character

while true do
    for _, workstation in pairs(game.Workspace.Environment.Locations.BloxyBurgers.CashierWorkstations:GetChildren()) do
        if workstation.Occupied.Value then
            local customer = workstation.Occupied.Value
            local order = customer.Order
            local burger = order.Burger.Value
            local fries = order.Fries.Value
            local cola = order.Cola.Value

            if burger and fries and cola then
                game.ReplicatedStorage.DeliverFoodEvent:FireServer(workstation)
            end
        end
    end
    wait(1)
end
```

*Script 3: Auto-Trabalhar como Cabelereiro*

```
local player = game.Players.LocalPlayer
local character = player.Character

while true do
    for _, workstation in pairs(game.Workspace.Environment.Locations.StylezHairStudio.HairdresserWorkstations:GetChildren()) do
        if workstation.Occupied.Value then
            local customer = workstation.Occupied.Value
            local style = customer.Order.Style.Value
            local color = customer.Order.Color.Value

            if style and color then
                game.ReplicatedStorage.HairdresserEvent:FireServer(workstation, style, color)
            end
        end
    end
    wait(1)
end
```
