# Info
New (default) Blazor Server project. Two things are changed/added.
- In **Shared/MainLayout.razor**, I added logging for **OnInitialized** and **Dispose** to see what goes wrong
- In **Pages/_Host.cshtml**, the render-mode of the App is changed to **Server** instead of **ServerPrerendered**, this is the part that makes the difference, having the render-mode on **ServerPrerendered** will not give any issues. 

# Steps to reproduce
Tested on Edge and Chrome with dotnet version 7.0.403
1. Install Surfshark extension (connecting makes no difference, important is that it is installed)
2. Cd into cd .\SurfsharkBug\ and run the project with **dotnet run**
3. Navigate to the provided url (http://localhost:5292)
4. Refresh the page a few times

The log in command will show only Initialize. After a minute or so the Dispose log will also show up.

6. Disable the Surfshark extension in the browser.
7. Refresh the page a few times

This time you will see both Initialize and Dispose on refresh
