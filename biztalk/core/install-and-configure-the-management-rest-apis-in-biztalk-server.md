---
title: "Instalar y configurar las API de REST de administración | Documentos de Microsoft"
description: "Consultar los artefactos en su entorno de BizTalk mediante datos de administración de API de REST con Feature Pack en BizTalk Server"
ms.custom: fp1
ms.date: 11/06/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e05b122047d7e303ed4e187fec19725cce9ae398
ms.sourcegitcommit: 30189176c44873e3de42cc5f2b8951da51ffd251
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a><span data-ttu-id="b2af1-103">Instalar y configurar las API de REST de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="b2af1-103">Install and configure the management REST APIs in BizTalk Server</span></span>

## <a name="what-are-management-data-apis"></a><span data-ttu-id="b2af1-104">¿Cuáles son los datos de administración de API</span><span class="sxs-lookup"><span data-stu-id="b2af1-104">What are management data APIs</span></span>
<span data-ttu-id="b2af1-105">API de datos de administración son puntos de conexión que pueden actualizar, agregar y consultar el estado de diferentes artefactos de forma remota su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="b2af1-105">Management data APIs are endpoints that let you remotely update, add, and query the status of different artifacts in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="b2af1-106">Los puntos de conexión se agregan con REST y vienen con una definición de swagger.</span><span class="sxs-lookup"><span data-stu-id="b2af1-106">The endpoints are added using REST, and come with a swagger definition.</span></span> 

<span data-ttu-id="b2af1-107">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , hay un script de Windows PowerShell que instale estas API de REST y sus definiciones de swagger.</span><span class="sxs-lookup"><span data-stu-id="b2af1-107">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, there's a Windows PowerShell script that installs these REST APIs, and their swagger definitions.</span></span> <span data-ttu-id="b2af1-108">Estas API realizan llamadas REST para administrar de forma remota los puertos, orquestaciones, socios, acuerdos, canalizaciones y mucho más.</span><span class="sxs-lookup"><span data-stu-id="b2af1-108">These APIs make REST calls to remotely manage ports, orchestrations, partners, agreements, pipelines, and more.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b2af1-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b2af1-109">Prerequisites</span></span>
* <span data-ttu-id="b2af1-110">Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2af1-110">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

* <span data-ttu-id="b2af1-111">Instalar IIS en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2af1-111">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b2af1-112">En la mayoría [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos, IIS ya está instalado.</span><span class="sxs-lookup"><span data-stu-id="b2af1-112">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="b2af1-113">Vea [requisitos de Hardware y Software para BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="b2af1-113">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span> <span data-ttu-id="b2af1-114">Confirme que IIS está instalado en el servidor de BizTalk abriendo **Administrador de Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="b2af1-114">Confirm IIS is installed on the BizTalk Server by opening **Internet Information Services Manager**.</span></span> 

## <a name="step-1-install-the-rest-apis"></a><span data-ttu-id="b2af1-115">Paso 1: Instalar la API de REST</span><span class="sxs-lookup"><span data-stu-id="b2af1-115">Step 1: Install the REST APIs</span></span>

1. <span data-ttu-id="b2af1-116">Ejecutar Windows PowerShell como administrador (**iniciar** menú, escriba **PowerShell**, haga clic y seleccione **ejecutar como administrador**).</span><span class="sxs-lookup"><span data-stu-id="b2af1-116">Run Windows PowerShell as Administrator (**Start** menu, type **PowerShell**, right click, and select **Run as administrator**).</span></span> 
2. <span data-ttu-id="b2af1-117">Vaya a la carpeta de instalación de BizTalk (por ejemplo, escriba: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`).</span><span class="sxs-lookup"><span data-stu-id="b2af1-117">Go to the BizTalk installation folder (for example, type: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`).</span></span>
3. <span data-ttu-id="b2af1-118">En el siguiente texto, reemplace `Default Web Site`, `mgmtServiceAppPool`, `domain/user`, `password`, y `domain\group` con sus valores:</span><span class="sxs-lookup"><span data-stu-id="b2af1-118">In the following text, replace `Default Web Site`, `mgmtServiceAppPool`, `domain/user`, `password`, and `domain\group` with your values:</span></span>

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```

    <span data-ttu-id="b2af1-119">En el ejemplo siguiente, se utiliza el `Default Web Site`, cree un grupo de aplicaciones denominado `RESTAppPool`, ejecute el grupo de aplicaciones como el `bootcampbts2016\btsservice` , utilice `BIZTALK-serviceacct` como la contraseña de la cuenta de usuario y otorgar permisos de grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="b2af1-119">In the following example, we use the `Default Web Site`, create an application pool named `RESTAppPool`, run the appPool as the `bootcampbts2016\btsservice` account, use `BIZTALK-serviceacct` as the user account password, and give the BizTalk Server Administrators group permissions.</span></span> <span data-ttu-id="b2af1-120">No olvide escriba lo siguiente, incluido el único proporciona los valores que lo rodea con espacios:</span><span class="sxs-lookup"><span data-stu-id="b2af1-120">Be sure to enter the following, including the single quotes surrounding values with spaces:</span></span> 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName 'Default Web Site' -ApplicationPool RESTAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    <span data-ttu-id="b2af1-121">Cuando haya finalizado, el **BizTalkManagementService** aplicación se crea dentro de IIS:</span><span class="sxs-lookup"><span data-stu-id="b2af1-121">When complete, the **BizTalkManagementService** application is created within IIS:</span></span>  
    <span data-ttu-id="b2af1-122">![Aplicación de BizTalkManagementService](../core/media/biztalkmanagementservice-apppool.png)</span><span class="sxs-lookup"><span data-stu-id="b2af1-122">![BizTalkManagementService application](../core/media/biztalkmanagementservice-apppool.png)</span></span>

4. <span data-ttu-id="b2af1-123">Para confirmar que funciona, vaya a `http://localhost/BizTalkManagementService/swagger`.</span><span class="sxs-lookup"><span data-stu-id="b2af1-123">To confirm it’s working, browse to `http://localhost/BizTalkManagementService/swagger`.</span></span> <span data-ttu-id="b2af1-124">Si se le pedirá al inicio de sesión, inicie sesión con una cuenta que sea miembro de la domain\group que escribió en el paso anterior (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`).</span><span class="sxs-lookup"><span data-stu-id="b2af1-124">If you are prompted to sign-in, sign in with an account that is member of the domain\group you entered in the previous step (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`).</span></span> 

> [!WARNING]
> <span data-ttu-id="b2af1-125">La aplicación BizTalkManagementService en IIS usa un archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="b2af1-125">The BizTalkManagementService application in IIS uses a web.config file.</span></span> <span data-ttu-id="b2af1-126">Elementos en el archivo web.config **distinguen mayúsculas de minúsculas**.</span><span class="sxs-lookup"><span data-stu-id="b2af1-126">Elements within web.config **are case sensitive**.</span></span> <span data-ttu-id="b2af1-127">Por tanto, cuando se ejecuta la secuencia de comandos de Windows PowerShell, asegúrese de escribir las mayúsculas y minúsculas correctas para `-AuthorizationRoles` valor.</span><span class="sxs-lookup"><span data-stu-id="b2af1-127">So when you execute the Windows PowerShell script, be sure to enter the correct case for `-AuthorizationRoles` value.</span></span> <span data-ttu-id="b2af1-128">Si no está seguro del caso, aquí es una manera fácil de averiguar:</span><span class="sxs-lookup"><span data-stu-id="b2af1-128">If you’re not sure of the case, here’s an easy way to find out:</span></span> 
> 
> 1. <span data-ttu-id="b2af1-129">Abra **administración de equipos**y expanda **usuarios y grupos locales**.</span><span class="sxs-lookup"><span data-stu-id="b2af1-129">Open **Computer Management**, and expand **Local Users and Groups**.</span></span>
> 2. <span data-ttu-id="b2af1-130">Seleccione **grupos**y desplácese hacia abajo hasta la **SQLServer...**</span><span class="sxs-lookup"><span data-stu-id="b2af1-130">Select **Groups**, and scroll down to the **SQLServer…**</span></span> <span data-ttu-id="b2af1-131">grupos.</span><span class="sxs-lookup"><span data-stu-id="b2af1-131">groups.</span></span> 
> 3. <span data-ttu-id="b2af1-132">En el ejemplo siguiente, observe **BOOTCAMPBTS2016** esté en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="b2af1-132">In the following example, notice **BOOTCAMPBTS2016** is in all caps.</span></span> <span data-ttu-id="b2af1-133">Si ve todo en mayúsculas, a continuación, escriba el nombre del equipo en todo en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="b2af1-133">If you see all caps, then enter the computer name in all caps.</span></span> 
> 
> ![Nombre del equipo está en mayúsculas](../core/media/groups-case.png)

<span data-ttu-id="b2af1-135">Ahora que las API de REST se exponen a través de IIS, puede obtener acceso a y ejecutados por otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b2af1-135">Now that the REST APIs are exposed through IIS, they can be accessed and executed by other applications.</span></span> 

<span data-ttu-id="b2af1-136">Puede cambiar quién tiene acceso mediante la actualización manual del **web.config** archivo, que se encuentra en la carpeta raíz de la aplicación de administración.</span><span class="sxs-lookup"><span data-stu-id="b2af1-136">You can change who has access by manually updating the **web.config** file, which is in the root folder of the management application.</span></span> <span data-ttu-id="b2af1-137">Por ejemplo, utilice los procedimientos siguientes para permitir que cualquier usuario acceso a la swagger de salida:</span><span class="sxs-lookup"><span data-stu-id="b2af1-137">For example, use the following to allow anyone access to the swagger output:</span></span> 

```
<authorization>
   <allow users="*" />
</authorization>
```

## <a name="step-2-test-the-apis"></a><span data-ttu-id="b2af1-138">Paso 2: Probar la API</span><span class="sxs-lookup"><span data-stu-id="b2af1-138">Step 2: Test the APIs</span></span>

1. <span data-ttu-id="b2af1-139">En el servidor BizTalk Server, vaya a `http://localhost/BizTalkManagementService/swagger`.</span><span class="sxs-lookup"><span data-stu-id="b2af1-139">On the BizTalk Server, browse to `http://localhost/BizTalkManagementService/swagger`.</span></span>

2. <span data-ttu-id="b2af1-140">Desplácese a **Hosts**y seleccione **mostrar/ocultar**.</span><span class="sxs-lookup"><span data-stu-id="b2af1-140">Scroll to **Hosts**, and select **Show/Hide**.</span></span> <span data-ttu-id="b2af1-141">Hay un comando GET; Haga clic en esta fila:</span><span class="sxs-lookup"><span data-stu-id="b2af1-141">There is a GET command; click this row:</span></span>  
<span data-ttu-id="b2af1-142">![OBTENER todos los hosts](../core/media/managment-rest-apis-hosts-get.png)</span><span class="sxs-lookup"><span data-stu-id="b2af1-142">![GET all hosts](../core/media/managment-rest-apis-hosts-get.png)</span></span>

3. <span data-ttu-id="b2af1-143">Muestra los detalles.</span><span class="sxs-lookup"><span data-stu-id="b2af1-143">It shows the details.</span></span> <span data-ttu-id="b2af1-144">Seleccione **Pruébelo**:</span><span class="sxs-lookup"><span data-stu-id="b2af1-144">Select **Try it out**:</span></span>  
<span data-ttu-id="b2af1-145">![Pruébelo](../core/media/managment-rest-apis-hosts-tryitout.png)</span><span class="sxs-lookup"><span data-stu-id="b2af1-145">![Try it out](../core/media/managment-rest-apis-hosts-tryitout.png)</span></span>

4. <span data-ttu-id="b2af1-146">El cuerpo de respuesta devuelve todos los hosts:</span><span class="sxs-lookup"><span data-stu-id="b2af1-146">The Response Body returns all the hosts:</span></span>  
![Respuestas](../core/media/managment-rest-apis-hosts-response.png)

> [!NOTE]
> <span data-ttu-id="b2af1-148">Si llega hasta `http://localhost/BizTalkManagementService`, obtendrá un error 500.</span><span class="sxs-lookup"><span data-stu-id="b2af1-148">If you browse to `http://localhost/BizTalkManagementService`, you should get a 500 error.</span></span> <span data-ttu-id="b2af1-149">Es bueno.</span><span class="sxs-lookup"><span data-stu-id="b2af1-149">That’s a good thing.</span></span> <span data-ttu-id="b2af1-150">Basta con agregar `/swagger` al final de la dirección URL y, verá las API de REST disponible.</span><span class="sxs-lookup"><span data-stu-id="b2af1-150">Just add `/swagger` to the end of URL, and you’ll see the available REST APIs.</span></span> 


## <a name="see-also"></a><span data-ttu-id="b2af1-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2af1-151">See also</span></span>
 [<span data-ttu-id="b2af1-152">Configurar el Feature Pack</span><span class="sxs-lookup"><span data-stu-id="b2af1-152">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)