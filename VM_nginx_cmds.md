az vm create
--resource-group learn-b92f53f2-b53e-4b32-a997-3aad863c2df6
--name my-vm
--image UbuntuLTS
--admin-username azureuser
--generate-ssh-keys

az vm extension set
--resource-group learn-b92f53f2-b53e-4b32-a997-3aad863c2df6
--vm-name my-vm
--name customScript
--publisher Microsoft.Azure.Extensions
--version 2.1
--settings '{"fileUris":["https://raw.githubusercontent.com/MicrosoftDocs/mslearn-welcome-to-azure/master/configure-nginx.sh"]}'
--protected-settings '{"commandToExecute": "./configure-nginx.sh"}'
