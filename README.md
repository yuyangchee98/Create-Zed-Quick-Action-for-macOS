# Create Zed Quick Action for macOS

Creating a Quick Action in macOS that allows you to right-click any folder and open it directly in Zed editor.

## Quick Action Script

```bash
#!/bin/bash

# Get the selected folder path from Automator
for f in "$@"
do
    # Check if the path exists
    if [ -d "$f" ]; then
        # Open Zed with the folder
        /usr/local/bin/zed "$f"
    fi
done
```

## Setup Instructions

1. Open **Automator** (you can use Spotlight to find it)
2. Create a new **Quick Action** (File > New)
3. Set "Workflow receives" to **folders** in **Finder**
4. Add a **Run Shell Script** action (search for it in the actions library)
5. Copy the script above into the shell script box
6. Set "Pass input" to **as arguments**
7. Save the Quick Action with a name like "Open in Zed"
