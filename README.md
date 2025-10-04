# Visual Studio Code - UI Library
<img width="874" height="613" alt="image" src="https://github.com/user-attachments/assets/c174149e-3db9-469a-a896-6c032ca75585" />
<img width="720" height="365" alt="image" src="https://github.com/user-attachments/assets/99c8a051-5867-42d4-857d-1f62d9697b96" />

```lua
local Library = loadstring(game:HttpGet('https://github.com/realkhaw/VScode/blob/main/main.luau?raw=true', true))()

local app = Library:app({
	Title = "Visual Studio Code - 1.25.8",
	Footer = "Made by @96soul",
	Enums = Enum.KeyCode.F1
})

local Tabs = app:Normal(77072339158371) do 
	local Element = Tabs:Element('Bitdancer.json', "Contains settings and options for Bitdancer features.") do
		Element:Paragarp({
			Title = "Paragarp",
			Desc = "Displays a paragraph of descriptive or informational text to guide the user."
		})

		Element:Toggle({
			Title = "Toggle",
			Desc = "A switch that can be turned on or off to enable or disable a specific feature.",
			Value = false,
			Call = print
		})

		Element:Button({
			Title = "Button",
			Desc = "A clickable button that executes an action or command when pressed.",
			Call = function()
				print('Click')
			end,
		})

		Element:Textfield({
			Title = "Textfield",
			Desc = "An input field where the user can type or enter custom text or data.",
			Value = "1225554",
			Call = function(v)
				print(v)
			end,
		})

		Element:Slider({
			Title = "Slider",
			Desc = "A horizontal slider that lets the user adjust a numeric value within a specific range.",
			Value = 50,
			Min = 1,
			Max = 100,
			Rounding = 2,
			Call = function(value)
				print(value)
			end,
		})

		local a = {}

		for i = 1, 40 do
			table.insert(a, tostring(i))
		end

		Element:List({
			Title = "Dropdown (Multi)",
			Desc = "A dropdown list allowing the user to select a numeric value between 1 and 40.",
			List = a,
			Value = a,
			Call = function(v)
				print(v)
			end,
		})

		Element:List({
			Title = "Dropdown (Simple)",
			Desc = "A dropdown list allowing the user to choose between different fruits: Apple, Banana, or Melon.",
			List = {"Apple", "Banana", "Melon"},
			Value = "Apple",
			Call = function(v)
				print(v)
			end,
		})
	end
end
```
