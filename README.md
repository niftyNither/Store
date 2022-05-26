# Store
app_www

## Steps for succesful instalation 

[Docker container]
docker run -it --rm \-p 5050:5050 \
-v /tmp/dotnet-5-docker:/src \
mcr.microsoft.com/dotnet/sdk:5.0

[trust certs]
dotnet dev-certs https --trust

[dotnet-aspnet-codegenerator]
dotnet tool install --global dotnet-aspnet-codegenerator --version 5.0.0-preview.8.20419.1

<code gen>
 dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design -v 5.0.0

[Remember to export path]
export PATH="$PATH:/root/.dotnet/tools"

<repeat operation>
* dotnet-aspnet-codegenerator controller -udl -dc ApplicationDbContext  -sqlite -outDir Controllers -m Customer -name CustomerController

* dotnet-aspnet-codegenerator controller -udl -dc ApplicationDbContext  -sqlite -outDir Controllers -m InvoiceItem -name InvoiceItemController

* dotnet-aspnet-codegenerator controller -udl -dc ApplicationDbContext  -sqlite -outDir Controllers -m Invoice -name InvoiceController