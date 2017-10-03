---
title: "Instalar y configurar las API de REST de administración | Documentos de Microsoft"
description: "Consultar el estado de los artefactos en su entorno de BizTalk mediante datos de administración de API de REST con Feature Pack 1 de BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: "8"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 009b3b0bb333b8f92f6235da57b0c3e9f5daca96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a><span data-ttu-id="bcd7f-103">Instalar y configurar las API de REST de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="bcd7f-103">Install and configure the management REST APIs in BizTalk Server</span></span>
<span data-ttu-id="bcd7f-104">Usar un script de Windows PowerShell para habilitar las API de REST que administrar de forma remota su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcd7f-104">Use a Windows PowerShell script to enable REST APIs that remotely manage your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="what-are-management-data-apis"></a><span data-ttu-id="bcd7f-105">¿Cuáles son los datos de administración de API</span><span class="sxs-lookup"><span data-stu-id="bcd7f-105">What are Management data APIs</span></span>
<span data-ttu-id="bcd7f-106">API de datos de administración son los extremos que pueden actualizar, agregar y consultar el estado de diferentes artefactos de forma remota su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="bcd7f-106">Management data APIs are the endpoints that let you remotely update, add, and query the status of different artifacts in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="bcd7f-107">Los puntos de conexión se agregan con REST y vienen con una definición de Swagger.</span><span class="sxs-lookup"><span data-stu-id="bcd7f-107">The endpoints are added using REST, and come with a Swagger definition.</span></span> 

<span data-ttu-id="bcd7f-108">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , hay un script de Windows PowerShell que instale estas API de REST y sus definiciones de swagger.</span><span class="sxs-lookup"><span data-stu-id="bcd7f-108">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, there's a Windows PowerShell script that installs these REST APIs, and their swagger definitions.</span></span> <span data-ttu-id="bcd7f-109">Estas API realizan llamadas REST para administrar de forma remota los puertos, orquestaciones, socios, acuerdos, canalizaciones y mucho más.</span><span class="sxs-lookup"><span data-stu-id="bcd7f-109">These APIs make REST calls to remotely manage ports, orchestrations, partners, agreements, pipelines, and more.</span></span> 

<span data-ttu-id="bcd7f-110">En este tema se muestra cómo instalar las API de REST.</span><span class="sxs-lookup"><span data-stu-id="bcd7f-110">This topic shows you how to install the REST APIs.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bcd7f-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bcd7f-111">Prerequisites</span></span>
* <span data-ttu-id="bcd7f-112">Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcd7f-112">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

* <span data-ttu-id="bcd7f-113">Instalar IIS en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcd7f-113">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="bcd7f-114">En la mayoría [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos, IIS ya está instalado.</span><span class="sxs-lookup"><span data-stu-id="bcd7f-114">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="bcd7f-115">Vea [requisitos de Hardware y Software para BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="bcd7f-115">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span>

## <a name="enable-the-rest-apis"></a><span data-ttu-id="bcd7f-116">Habilitar las API de REST</span><span class="sxs-lookup"><span data-stu-id="bcd7f-116">Enable the REST APIs</span></span>

1. <span data-ttu-id="bcd7f-117">Ejecutar Windows PowerShell como administrador (**iniciar** menú, escriba **PowerShell**, haga clic y seleccione **ejecutar como administrador**).</span><span class="sxs-lookup"><span data-stu-id="bcd7f-117">Run Windows PowerShell as Administrator (**Start** menu, type **PowerShell**, right click, and select **Run as administrator**).</span></span> 
2. <span data-ttu-id="bcd7f-118">Vaya a la carpeta de BizTalk en **(x86) de archivos de programa/Microsoft BizTalk Server 2016**</span><span class="sxs-lookup"><span data-stu-id="bcd7f-118">Browse to the BizTalk folder under **Program Files (x86)/Microsoft BizTalk Server 2016**</span></span>
3. <span data-ttu-id="bcd7f-119">Ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="bcd7f-119">Run the following command.</span></span> <span data-ttu-id="bcd7f-120">Asegúrese de actualizar su `website`, `domain/user`, `password`, y `domain\group` con sus valores:</span><span class="sxs-lookup"><span data-stu-id="bcd7f-120">Be sure to update your `website`, `domain/user`, `password`, and `domain\group` with your values:</span></span> 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```
4. <span data-ttu-id="bcd7f-121">Después de ejecutar la secuencia de comandos, busque la nueva aplicación de IIS:</span><span class="sxs-lookup"><span data-stu-id="bcd7f-121">After you run the script, browse the new IIS application:</span></span>  
    1. <span data-ttu-id="bcd7f-122">Abra el explorador web</span><span class="sxs-lookup"><span data-stu-id="bcd7f-122">Open your web browser</span></span>
    2. <span data-ttu-id="bcd7f-123">Vaya a **http://localhost/OperationalDataService/swagger**</span><span class="sxs-lookup"><span data-stu-id="bcd7f-123">Browse to **http://localhost/OperationalDataService/swagger**</span></span>

5. <span data-ttu-id="bcd7f-124">Las cargas de las definiciones de Swagger.</span><span class="sxs-lookup"><span data-stu-id="bcd7f-124">The Swagger definitions loads.</span></span> <span data-ttu-id="bcd7f-125">También puede cambiar quién tiene acceso mediante la actualización de la **web.config** archivo en la carpeta raíz de la aplicación de administración.</span><span class="sxs-lookup"><span data-stu-id="bcd7f-125">You can also change who has access by updating the **web.config** file in the root folder of the Management Application.</span></span>

<span data-ttu-id="bcd7f-126">Las API de REST se exponen a través de la máquina y se puede obtener acceso a y ejecutadas por otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bcd7f-126">The REST APIs are exposed through the machine, and can be accessed and executed by other applications.</span></span> 


## <a name="see-also"></a><span data-ttu-id="bcd7f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcd7f-127">See also</span></span>
 [<span data-ttu-id="bcd7f-128">Configurar el Feature Pack</span><span class="sxs-lookup"><span data-stu-id="bcd7f-128">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)