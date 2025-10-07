# Visual Studio Code - UI Library
<img width="874" height="613" alt="image" src="https://github.com/user-attachments/assets/c174149e-3db9-469a-a896-6c032ca75585" />
<img width="720" height="365" alt="image" src="https://github.com/user-attachments/assets/99c8a051-5867-42d4-857d-1f62d9697b96" />

```lua
local Library = loadstring(game:HttpGet('https://github.com/realkhaw/VScode/blob/main/main.luau?raw=true', true))()

local app = Library:app({
	Title = "Visual Studio Code - 1.25.8",
	Footer = "Made by @96soul",
	Enums = Enum.KeyCode.Q
})

local Tabs = app:Normal(77072339158371) do 
	local Element = Tabs:Element('Bitdancer.json', "Contains settings and options for Bitdancer features.") do
		local Island = Element:Paragarp({
			Title = "Paragarp",
			Icon = 119298828316399,
			Status = false,
			Desc = "Displays a paragraph of descriptive or informational text."
		})
		
		Element:Banner({})

		local a = Element:Toggle({
			Title = "Toggle",
			Icon = 119298828316399,
			Value = false,
			Call = function(v)
				Island:SetStatus(v)
			end,
		})

		a.OnValueChanged:Connect(function(value)
			print(value)
		end)

		Element:Button({
			Title = "Button",
			Icon = 119298828316399,
			Desc = "A clickable button that executes.",
			Call = function()
				--Notification.new("error", "Error Heading", "Error body message.", true, 3)
				--Notification.new("success", "Success Heading", "Success body message.", true, 3) 
			end,
		})

		Element:Textfield({
			Title = "Textfield",
			Icon = 119298828316399,
			Desc = "An input field where the user can type.",
			Value = "1225554",
			Call = function(v)
				print(v)
			end,
		})

		local Slider = Element:Slider({
			Title = "Slider",
			Icon = 119298828316399,
			Desc = "Select Y Position.",
			Value = 50,
			Min = 1,
			Max = 100,
			Rounding = 2,
			Call = function(value)

			end,
		})

		Slider.OnValueChanged:Connect(function(value)
			game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = value
		end)
		
		local Simple = Element:Dropdown({
			Title = "Dropdown (Multi)",
			Icon = 119298828316399,
			Type = 'Double',
			Advance = { -- if not want then place {}
				['Select'] = "เลือกแล้ว",
				['Not Select'] = "ยังไม่ได้เลือก",
				['Clear'] = "เคลียร์",
				['Select All'] = "เลือกทั้งหมด",
				['Search'] = "ค้นหา"
			},
			Multi = true,
			Desc = "A dropdown list allowing the user to select.",
			List = {
				{
					Title = "Hello",
				},
				{
					Title = "EZ",
				}
			},
			Value = "Hello"
		})
		
		Simple.OnValueChanged:Connect(function(v)
			print(v)
		end)
		
		Simple.OnRefresh:Connect(function(self)
			local Players = game:GetService("Players")
			for _, v in pairs(Players:GetChildren()) do
				local thumbType = Enum.ThumbnailType.AvatarThumbnail
				local thumbSize = Enum.ThumbnailSize.Size420x420
				local content, isReady = Players:GetUserThumbnailAsync(v.UserId, thumbType, thumbSize)

				self:AddList({
					Title = v.Name,
					Icon = content,
				})
			end
		end)
		
		local Multi = Element:Dropdown({
		Title = "Dropdown (Multi)",
		Icon = 119298828316399,
		Desc = "A dropdown list allowing the user to select.",
		List = a,
		Multi = true,
		Value = a,
		})
		
		
	end
end
```
