-- Sistema de Keys para Loadstring - Bringitems Script
-- Formato da Key: "Taf-letras_aleatorias-99-noites"
-- URL Protegida: https://raw.githubusercontent.com/Bac0nHck/Scripts/refs/heads/main/bringitems.lua

local KeySystem = {}

-- Configurações do sistema
local CONFIG = {
    PREFIX = "Taf",
    SUFFIX = "noites",
    NUMBER = "99",
    SEPARATOR = "-",
    SCRIPT_URL = "https://raw.githubusercontent.com/Bac0nHck/Scripts/refs/heads/main/bringitems.lua"
}

-- Lista de keys válidas (100 keys no total)
local validKeys = {
    -- Keys originais (10)
    "taf-x7k9m2-99-noites",
    "taf-q8w3rt-99-noites", 
    "taf-mn7bv4-99-noites",
    "taf-zx9cv3-99-noites",
    "taf-pl2ok8-99-noites",
    "taf-gh5ty1-99-noites",
    "taf-vb3nm6-99-noites",
    "taf-df8ju4-99-noites",
    "taf-sw6er9-99-noites",
    "taf-as4df7-99-noites",
    
    -- Novas 90 keys adicionadas
    "taf-mk9pl3-99-noites",
    "taf-rt7yu2-99-noites",
    "taf-bg4hn8-99-noites",
    "taf-vf6cz1-99-noites",
    "taf-qw5er7-99-noites",
    "taf-ty9ui4-99-noites",
    "taf-op3as6-99-noites",
    "taf-df8gh2-99-noites",
    "taf-jk5lm9-99-noites",
    "taf-zx1cv3-99-noites",
    "taf-bn7vm4-99-noites",
    "taf-er2ty8-99-noites",
    "taf-ui6op1-99-noites",
    "taf-as9df5-99-noites",
    "taf-gh3jk7-99-noites",
    "taf-lz2xc4-99-noites",
    "taf-vb8nm6-99-noites",
    "taf-qw1er9-99-noites",
    "taf-ty5rt3-99-noites",
    "taf-yu7ui2-99-noites",
    "taf-op4as8-99-noites",
    "taf-df6gh1-99-noites",
    "taf-jk9lm5-99-noites",
    "taf-zx3cv7-99-noites",
    "taf-bn4vm2-99-noites",
    "taf-er8ty6-99-noites",
    "taf-ui1op9-99-noites",
    "taf-as5df3-99-noites",
    "taf-gh7jk4-99-noites",
    "taf-lz6xc8-99-noites",
    "taf-vb2nm1-99-noites",
    "taf-qw9er5-99-noites",
    "taf-ty3rt7-99-noites",
    "taf-yu4ui6-99-noites",
    "taf-op8as2-99-noites",
    "taf-df1gh9-99-noites",
    "taf-jk5lm3-99-noites",
    "taf-zx7cv4-99-noites",
    "taf-bn6vm8-99-noites",
    "taf-er2ty1-99-noites",
    "taf-ui9op5-99-noites",
    "taf-as3df7-99-noites",
    "taf-gh4jk6-99-noites",
    "taf-lz8xc2-99-noites",
    "taf-vb1nm9-99-noites",
    "taf-qw5er3-99-noites",
    "taf-ty7rt4-99-noites",
    "taf-yu6ui8-99-noites",
    "taf-op2as1-99-noites",
    "taf-df9gh5-99-noites",
    "taf-jk3lm7-99-noites",
    "taf-zx4cv6-99-noites",
    "taf-bn8vm2-99-noites",
    "taf-er1ty9-99-noites",
    "taf-ui5op3-99-noites",
    "taf-as7df4-99-noites",
    "taf-gh6jk8-99-noites",
    "taf-lz2xc1-99-noites",
    "taf-vb9nm5-99-noites",
    "taf-qw3er7-99-noites",
    "taf-ty4rt6-99-noites",
    "taf-yu8ui2-99-noites",
    "taf-op1as9-99-noites",
    "taf-df5gh3-99-noites",
    "taf-jk7lm4-99-noites",
    "taf-zx6cv8-99-noites",
    "taf-bn2vm1-99-noites",
    "taf-er9ty5-99-noites",
    "taf-ui3op7-99-noites",
    "taf-as4df6-99-noites",
    "taf-gh8jk2-99-noites",
    "taf-lz1xc9-99-noites",
    "taf-vb5nm3-99-noites",
    "taf-qw7er4-99-noites",
    "taf-ty6rt8-99-noites",
    "taf-yu2ui1-99-noites",
    "taf-op9as5-99-noites",
    "taf-df3gh7-99-noites",
    "taf-jk4lm6-99-noites",
    "taf-zx8cv2-99-noites",
    "taf-bn1vm9-99-noites",
    "taf-er5ty3-99-noites",
    "taf-ui7op4-99-noites",
    "taf-as6df8-99-noites",
    "taf-gh2jk1-99-noites",
    "taf-lz9xc5-99-noites",
    "taf-vb3nm7-99-noites",
    "taf-qw4er6-99-noites",
    "taf-ty8rt2-99-noites",
    "taf-yu1ui9-99-noites",
    "taf-op5as3-99-noites",
    "taf-df7gh4-99-noites",
    "taf-jk6lm8-99-noites",
    "taf-zx2cv1-99-noites"
}

-- Lista de keys usadas (para evitar reutilização)
local usedKeys = {}

-- Função para gerar string aleatória
function KeySystem.generateRandomString(length)
    local chars = "abcdefghijklmnopqrstuvwxyz0123456789"
    local result = ""
    math.randomseed(tick())
    
    for i = 1, length do
        local randomIndex = math.random(1, #chars)
        result = result .. string.sub(chars, randomIndex, randomIndex)
    end
    
    return result
end

-- Função para gerar nova key
function KeySystem.generateKey()
    local randomPart = KeySystem.generateRandomString(6)
    return CONFIG.PREFIX .. CONFIG.SEPARATOR .. randomPart .. CONFIG.SEPARATOR .. CONFIG.NUMBER .. CONFIG.SEPARATOR .. CONFIG.SUFFIX
end

-- Função para validar formato da key (corrigida)
function KeySystem.isValidFormat(key)
    -- Remove espaços e converte para minúsculo
    key = string.lower(string.gsub(key, "%s+", ""))
    
    -- Padrão mais flexível: Taf-xxxxxx-99-noites (6 ou mais caracteres alfanuméricos)
    local pattern = "^taf%-[a-z0-9]+%-99%-noites$"
    
    print("🔍 Verificando formato da key: " .. key)
    print("📝 Padrão esperado: taf-xxxxxx-99-noites")
    
    local isValid = string.match(key, pattern) ~= nil
    print("✅ Formato válido: " .. tostring(isValid))
    
    return isValid
end

-- Função para verificar se key existe e não foi usada (corrigida)
function KeySystem.isKeyValid(key)
    -- Normaliza a key (remove espaços e converte para minúsculo)
    key = string.lower(string.gsub(key, "%s+", ""))
    
    print("🔑 Verificando key: " .. key)
    
    -- Verifica se key foi usada
    for _, usedKey in ipairs(usedKeys) do
        if string.lower(usedKey) == key then
            print("❌ Key já utilizada!")
            return false, "Key já foi utilizada!"
        end
    end
    
    -- Verifica se key existe na lista válida (case insensitive)
    for _, validKey in ipairs(validKeys) do
        if string.lower(validKey) == key then
            print("✅ Key encontrada na lista válida!")
            return true, "Key válida!"
        end
    end
    
    print("❌ Key não encontrada na lista válida")
    return false, "Key não encontrada ou inválida!"
end

-- Função para marcar key como usada
function KeySystem.markKeyAsUsed(key)
    table.insert(usedKeys, key)
end

-- Interface visual moderna e atrativa
function KeySystem.createKeyInterface()
    -- Cria uma GUI moderna para inserir a key
    local screenGui = Instance.new("ScreenGui")
    local frame = Instance.new("Frame")
    local frameCorner = Instance.new("UICorner")
    local frameStroke = Instance.new("UIStroke")
    local title = Instance.new("TextLabel")
    local subtitle = Instance.new("TextLabel")
    local keyInput = Instance.new("TextBox")
    local inputCorner = Instance.new("UICorner")
    local submitButton = Instance.new("TextButton")
    local submitCorner = Instance.new("UICorner")
    local statusLabel = Instance.new("TextLabel")
    local closeButton = Instance.new("TextButton")
    local closeCorner = Instance.new("UICorner")
    
    screenGui.Name = "KeySystemGUI"
    screenGui.ResetOnSpawn = false
    screenGui.Parent = game.CoreGui
    
    -- Frame principal com design moderno
    frame.Name = "MainFrame"
    frame.Size = UDim2.new(0, 450, 0, 300)
    frame.Position = UDim2.new(0.5, -225, 0.5, -150)
    frame.BackgroundColor3 = Color3.fromRGB(25, 25, 35)
    frame.BorderSizePixel = 0
    frame.Active = true
    frame.Draggable = true
    frame.Parent = screenGui
    
    -- Cantos arredondados
    frameCorner.CornerRadius = UDim.new(0, 15)
    frameCorner.Parent = frame
    
    -- Borda brilhante
    frameStroke.Color = Color3.fromRGB(0, 150, 255)
    frameStroke.Thickness = 2
    frameStroke.Parent = frame
    
    -- Título principal
    title.Name = "Title"
    title.Size = UDim2.new(1, 0, 0, 50)
    title.Position = UDim2.new(0, 0, 0, 10)
    title.BackgroundTransparency = 1
    title.Text = "🔐 SISTEMA DE VERIFICAÇÃO"
    title.TextColor3 = Color3.fromRGB(255, 255, 255)
    title.TextSize = 20
    title.Font = Enum.Font.GothamBold
    title.Parent = frame
    
    -- Subtítulo
    subtitle.Name = "Subtitle"
    subtitle.Size = UDim2.new(1, 0, 0, 30)
    subtitle.Position = UDim2.new(0, 0, 0, 50)
    subtitle.BackgroundTransparency = 1
    subtitle.Text = "Bringitems Script - Digite sua key para continuar"
    subtitle.TextColor3 = Color3.fromRGB(180, 180, 180)
    subtitle.TextSize = 14
    subtitle.Font = Enum.Font.Gotham
    subtitle.Parent = frame
    
    -- Input da key com design moderno
    keyInput.Name = "KeyInput"
    keyInput.Size = UDim2.new(0.85, 0, 0, 45)
    keyInput.Position = UDim2.new(0.075, 0, 0.35, 0)
    keyInput.BackgroundColor3 = Color3.fromRGB(40, 40, 50)
    keyInput.BorderSizePixel = 0
    keyInput.PlaceholderText = "Taf-xxxxxx-99-noites"
    keyInput.PlaceholderColor3 = Color3.fromRGB(120, 120, 120)
    keyInput.Text = ""
    keyInput.TextColor3 = Color3.fromRGB(255, 255, 255)
    keyInput.TextSize = 16
    keyInput.Font = Enum.Font.Gotham
    keyInput.TextXAlignment = Enum.TextXAlignment.Center
    keyInput.Parent = frame
    
    inputCorner.CornerRadius = UDim.new(0, 8)
    inputCorner.Parent = keyInput
    
    -- Botão de verificar
    submitButton.Name = "SubmitButton"
    submitButton.Size = UDim2.new(0.4, 0, 0, 40)
    submitButton.Position = UDim2.new(0.075, 0, 0.6, 0)
    submitButton.BackgroundColor3 = Color3.fromRGB(0, 200, 100)
    submitButton.BorderSizePixel = 0
    submitButton.Text = "✓ VERIFICAR"
    submitButton.TextColor3 = Color3.fromRGB(255, 255, 255)
    submitButton.TextSize = 14
    submitButton.Font = Enum.Font.GothamBold
    submitButton.Parent = frame
    
    submitCorner.CornerRadius = UDim.new(0, 8)
    submitCorner.Parent = submitButton
    
    -- Botão de fechar
    closeButton.Name = "CloseButton"
    closeButton.Size = UDim2.new(0.4, 0, 0, 40)
    closeButton.Position = UDim2.new(0.525, 0, 0.6, 0)
    closeButton.BackgroundColor3 = Color3.fromRGB(200, 50, 50)
    closeButton.BorderSizePixel = 0
    closeButton.Text = "✕ FECHAR"
    closeButton.TextColor3 = Color3.fromRGB(255, 255, 255)
    closeButton.TextSize = 14
    closeButton.Font = Enum.Font.GothamBold
    closeButton.Parent = frame
    
    closeCorner.CornerRadius = UDim.new(0, 8)
    closeCorner.Parent = closeButton
    
    -- Status label
    statusLabel.Name = "StatusLabel"
    statusLabel.Size = UDim2.new(0.9, 0, 0, 40)
    statusLabel.Position = UDim2.new(0.05, 0, 0.78, 0)
    statusLabel.BackgroundTransparency = 1
    statusLabel.Text = "⚡ Insira sua key de acesso para continuar"
    statusLabel.TextColor3 = Color3.fromRGB(255, 215, 0)
    statusLabel.TextSize = 13
    statusLabel.Font = Enum.Font.Gotham
    statusLabel.TextXAlignment = Enum.TextXAlignment.Center
    statusLabel.Parent = frame
    -- Efeitos visuais e animações (corrigido)
    local function animateButton(button, originalColor)
        local originalSize = button.Size
        local isHovering = false
        
        button.MouseEnter:Connect(function()
            if not isHovering then
                isHovering = true
                button:TweenSize(UDim2.new(originalSize.X.Scale, originalSize.X.Offset + 5, originalSize.Y.Scale, originalSize.Y.Offset + 2), "Out", "Quad", 0.15, true)
                button.BackgroundColor3 = Color3.fromRGB(
                    math.min(255, originalColor.R * 255 + 30),
                    math.min(255, originalColor.G * 255 + 30), 
                    math.min(255, originalColor.B * 255 + 30)
                )
            end
        end)
        
        button.MouseLeave:Connect(function()
            if isHovering then
                isHovering = false
                button:TweenSize(originalSize, "Out", "Quad", 0.15, true)
                button.BackgroundColor3 = originalColor
            end
        end)
    end
    
    animateButton(submitButton, Color3.fromRGB(0, 200, 100))
    animateButton(closeButton, Color3.fromRGB(200, 50, 50))
    
    -- Eventos dos botões
    submitButton.MouseButton1Click:Connect(function()
        local inputKey = keyInput.Text:gsub("%s+", "") -- Remove espaços
        
        if inputKey == "" then
            statusLabel.Text = "❌ Por favor, digite uma key!"
            statusLabel.TextColor3 = Color3.fromRGB(255, 100, 100)
            keyInput:TweenSize(UDim2.new(keyInput.Size.X.Scale * 1.1, 0, keyInput.Size.Y.Scale, 0), "Out", "Elastic", 0.3, true)
            wait(0.3)
            keyInput:TweenSize(UDim2.new(keyInput.Size.X.Scale / 1.1, 0, keyInput.Size.Y.Scale, 0), "Out", "Elastic", 0.3, true)
            return
        end
        
        statusLabel.Text = "🔄 Verificando key..."
        statusLabel.TextColor3 = Color3.fromRGB(100, 150, 255)
        
        -- Debug: mostra a key que está sendo verificada
        print("🎯 Key digitada: '" .. inputKey .. "'")
        
        wait(0.5) -- Reduzido para 0.5 segundos
        
        if not KeySystem.isValidFormat(inputKey) then
            statusLabel.Text = "❌ Formato inválido! Use: Taf-xxxxxx-99-noites"
            statusLabel.TextColor3 = Color3.fromRGB(255, 100, 100)
            print("❌ Formato inválido detectado")
            return
        end
        
        local isValid, message = KeySystem.isKeyValid(inputKey)
        print("📋 Resultado da validação: " .. tostring(isValid) .. " - " .. message)
        
        if isValid then
            statusLabel.Text = "✅ Key válida! Carregando script..."
            statusLabel.TextColor3 = Color3.fromRGB(100, 255, 100)
            
            -- Animação de sucesso
            frame:TweenSize(UDim2.new(frame.Size.X.Scale * 1.1, 0, frame.Size.Y.Scale * 1.1, 0), "Out", "Elastic", 0.5, true)
            frameStroke.Color = Color3.fromRGB(0, 255, 100)
            
            KeySystem.markKeyAsUsed(inputKey)
            
            wait(2)
            screenGui:Destroy()
            
            -- Executa o script protegido
            KeySystem.executeProtectedScript()
        else
            statusLabel.Text = "❌ " .. message
            statusLabel.TextColor3 = Color3.fromRGB(255, 100, 100)
            
            -- Animação de erro
            frame:TweenPosition(
                UDim2.new(0.5, -235, 0.5, -150), "Out", "Elastic", 0.1, true,
                function()
                    frame:TweenPosition(UDim2.new(0.5, -215, 0.5, -150), "Out", "Elastic", 0.1, true,
                        function()
                            frame:TweenPosition(UDim2.new(0.5, -225, 0.5, -150), "Out", "Elastic", 0.1, true)
                        end)
                end)
        end
    end)
    
    closeButton.MouseButton1Click:Connect(function()
        -- Animação de fechamento
        frame:TweenSize(UDim2.new(0, 0, 0, 0), "In", "Back", 0.3, true)
        wait(0.3)
        screenGui:Destroy()
        print("❌ Sistema de keys fechado pelo usuário")
    end)
    
    -- Permite pressionar Enter para verificar
    keyInput.FocusLost:Connect(function(enterPressed)
        if enterPressed then
            submitButton.MouseButton1Click:Fire()
        end
    end)
end

-- Função para executar o script protegido
function KeySystem.executeProtectedScript()
    local success, result = pcall(function()
        print("🚀 Carregando Bringitems Script...")
        print("📁 URL: " .. CONFIG.SCRIPT_URL)
        
        -- Executa o loadstring original
        loadstring(game:HttpGet(CONFIG.SCRIPT_URL))()
        
        print("✅ Script carregado com sucesso!")
    end)
    
    if not success then
        warn("❌ Erro ao carregar o script: " .. tostring(result))
        
        -- Cria notificação de erro
        game.StarterGui:SetCore("SendNotification", {
            Title = "Erro no Script";
            Text = "Falha ao carregar o Bringitems Script";
            Duration = 5;
        })
    else
        -- Notificação de sucesso
        game.StarterGui:SetCore("SendNotification", {
            Title = "Script Carregado";
            Text = "Bringitems Script ativo!";
            Duration = 3;
        })
    end
end

-- Função para executar com key diretamente (sem GUI)
function KeySystem.executeWithKey(key)
    if not KeySystem.isValidFormat(key) then
        warn("❌ Formato de key inválido!")
        return false
    end
    
    local isValid, message = KeySystem.isKeyValid(key)
    
    if isValid then
        print("✅ " .. message)
        KeySystem.markKeyAsUsed(key)
        KeySystem.executeProtectedScript()
        return true
    else
        warn("❌ " .. message)
        return false
    end
end

-- Função principal - mostra a interface
function KeySystem.start()
    KeySystem.createKeyInterface()
end

-- Função para listar keys válidas (apenas para teste)
function KeySystem.listValidKeys()
    print("=== KEYS VÁLIDAS DISPONÍVEIS ===")
    for i, key in ipairs(validKeys) do
        local isUsed = false
        for _, usedKey in ipairs(usedKeys) do
            if usedKey == key then
                isUsed = true
                break
            end
        end
        
        local status = isUsed and " [USADA]" or " [DISPONÍVEL]"
        print(i .. ". " .. key .. status)
    end
    print("================================")
end

-- INICIALIZAÇÃO AUTOMÁTICA - ABRE O PAINEL IMEDIATAMENTE
print("🔐 Sistema de Keys carregado!")
print("📋 Keys disponíveis: " .. #validKeys)
print("🎮 Abrindo painel de verificação...")

-- Abre o painel automaticamente
KeySystem.start()

return KeySystem
