# HA Morse Code Lights
A Home Assistant script that allows users to send Morse code messages by flashing a switch-controlled light.

Built as a part of **Idiot Soup Jam**, week one: Signal.

---

## Requirements
- Home Assistant.
- A 'switch-controlled' light exposed as a 'switch.' entity within HA. I have only tested with a Shelly Plus 1.

---

## Installation
1. Navigate to **Settings > Automations & Scenes > Scripts**.
2. Then click **Add Script** > **Create new script**.
3. Click the three-dot menu > **Edit in YAML**.
4. Paste the contents of `morse_code_lights.yaml` into the editor.
5. Click **Save**.

---

## Usage
1. Go to **Settings > Automations & Scenes > Scripts**.
2. Find **Morse Code Lights** and click the **Run** button.
3. Fill in the fields and hit **Run**.

---

## Encoding workaround
Letters like S (`...`) and O (`---`) cause the following error `object of type 'ellipsis' has no len()`, due to the way HA interprets unquoted versions of these strings. As a workaround the morse map internally uses `d` for dot and `a` for dash, plain alphabetic characters that HA's editor has no reason to strip quotes from and Python has no reason to misinterpret.
