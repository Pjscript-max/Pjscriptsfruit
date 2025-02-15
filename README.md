# Pjscriptsfruit-- Simula uma Chuva de Fruta V4

local spawnPosition = Vector3.new(0, 100, 0) -- Defina a posição do spawn
local fruitModels = {"FruitModel1", "FruitModel2", "FruitModel3"} -- Nome dos modelos de frutas no jogo

-- Função para criar a chuva de frutas
local function spawnFruit()
    while true do
        wait(10)  -- Espera 10 segundos para cada fruta aparecer

        local fruit = Instance.new("Model")
        fruit.Name = fruitModels[math.random(1, #fruitModels)]
        fruit.Parent = workspace
        fruit:SetPrimaryPartCFrame(CFrame.new(spawnPosition))

        -- Simula uma fruta caindo do céu
        local bodyVelocity = Instance.new("BodyVelocity")
        bodyVelocity.MaxForce = Vector3.new(10000, 10000, 10000)
        bodyVelocity.Velocity = Vector3.new(0, -50, 0)
        bodyVelocity.Parent = fruit.PrimaryPart
    end
end

-- Iniciar a chuva de frutas
spawnFruit()
