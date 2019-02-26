---
title: Instalar y configurar las API de REST de administración | Microsoft Docs
description: Consultar los artefactos en su entorno de BizTalk mediante datos de administración de API de REST con Feature Pack en BizTalk Server
ms.custom: fp1
ms.date: 02/25/2019
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 680b7390462a7a64d3064f621b2011952ba2551c
ms.sourcegitcommit: 0e14c3e018b091d81d0e4a68fafc10f6e31697e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "56828569"
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a><span data-ttu-id="96c98-103">Instalar y configurar las API de REST de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="96c98-103">Install and configure the management REST APIs in BizTalk Server</span></span>

## <a name="what-are-management-data-apis"></a><span data-ttu-id="96c98-104">¿Cuáles son los datos de administración de API</span><span class="sxs-lookup"><span data-stu-id="96c98-104">What are management data APIs</span></span>
<span data-ttu-id="96c98-105">Datos de administración de API son puntos de conexión que le permiten actualizar, agregar y consultar el estado de los diferentes artefactos de forma remota su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="96c98-105">Management data APIs are endpoints that let you remotely update, add, and query the status of different artifacts in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="96c98-106">Los puntos de conexión se agregan mediante REST y viene acompañado de una definición de swagger.</span><span class="sxs-lookup"><span data-stu-id="96c98-106">The endpoints are added using REST, and come with a swagger definition.</span></span> 

<span data-ttu-id="96c98-107">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , hay un script de Windows PowerShell que instale estas API de REST y sus definiciones de swagger.</span><span class="sxs-lookup"><span data-stu-id="96c98-107">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, there's a Windows PowerShell script that installs these REST APIs, and their swagger definitions.</span></span> <span data-ttu-id="96c98-108">Estas API facilitan las llamadas REST para administrar de forma remota los puertos, orquestaciones, socios, acuerdos, canalizaciones y mucho más.</span><span class="sxs-lookup"><span data-stu-id="96c98-108">These APIs make REST calls to remotely manage ports, orchestrations, partners, agreements, pipelines, and more.</span></span> 

<span data-ttu-id="96c98-109">Para ver las API disponibles y qué puede hacer, consulte [referencia de API de REST de característica Pack](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016).</span><span class="sxs-lookup"><span data-stu-id="96c98-109">To see the available APIs, and what you can do, see [Feature Pack REST API reference](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="96c98-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="96c98-110">Prerequisites</span></span>
* <span data-ttu-id="96c98-111">Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96c98-111">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

* <span data-ttu-id="96c98-112">Instalar IIS en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96c98-112">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="96c98-113">Confirme que IIS está instalado en el servidor BizTalk Server, abra **Administrador de Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="96c98-113">Confirm IIS is installed on the BizTalk Server by opening **Internet Information Services Manager**.</span></span> 

  <span data-ttu-id="96c98-114">En la mayoría [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos, IIS ya está instalado.</span><span class="sxs-lookup"><span data-stu-id="96c98-114">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="96c98-115">Consulte [requisitos de Hardware y Software para BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="96c98-115">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span> 

## <a name="step-1-install-the-rest-apis"></a><span data-ttu-id="96c98-116">Paso 1: Instalar las API de REST</span><span class="sxs-lookup"><span data-stu-id="96c98-116">Step 1: Install the REST APIs</span></span>

1. <span data-ttu-id="96c98-117">Ejecutar Windows PowerShell como administrador (**iniciar** menú > tipo **PowerShell** > haga clic en > **ejecutar como administrador**).</span><span class="sxs-lookup"><span data-stu-id="96c98-117">Run Windows PowerShell as Administrator (**Start** menu > type **PowerShell** > right click > **Run as administrator**).</span></span> 
2. <span data-ttu-id="96c98-118">Vaya a la carpeta de instalación de BizTalk (por ejemplo, escriba: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`).</span><span class="sxs-lookup"><span data-stu-id="96c98-118">Go to the BizTalk installation folder (for example, type: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`).</span></span>
3. <span data-ttu-id="96c98-119">En el siguiente texto y reemplace `Default Web Site`, `mgmtServiceAppPool`, `domain/user`, `password`, y `domain\group` con sus valores:</span><span class="sxs-lookup"><span data-stu-id="96c98-119">In the following text, replace `Default Web Site`, `mgmtServiceAppPool`, `domain/user`, `password`, and `domain\group` with your values:</span></span>

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```

    <span data-ttu-id="96c98-120">En el ejemplo siguiente, usamos el `Default Web Site`, cree un grupo de aplicaciones denominado `RESTAppPool`, ejecutar el grupo de aplicaciones como la `bootcampbts2016\btsservice` cuenta, use `BIZTALK-serviceacct` como la contraseña de la cuenta de usuario y otorgar permisos de grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="96c98-120">In the following example, we use the `Default Web Site`, create an application pool named `RESTAppPool`, run the appPool as the `bootcampbts2016\btsservice` account, use `BIZTALK-serviceacct` as the user account password, and give the BizTalk Server Administrators group permissions.</span></span> <span data-ttu-id="96c98-121">Asegúrese de escribir lo siguiente, incluida la única proporciona los valores que lo rodea con espacios:</span><span class="sxs-lookup"><span data-stu-id="96c98-121">Be sure to enter the following, including the single quotes surrounding values with spaces:</span></span> 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName 'Default Web Site' -ApplicationPool RESTAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    <span data-ttu-id="96c98-122">Cuando haya finalizado, el **BizTalkManagementService** aplicación se crea dentro de IIS:</span><span class="sxs-lookup"><span data-stu-id="96c98-122">When complete, the **BizTalkManagementService** application is created within IIS:</span></span>  
    <span data-ttu-id="96c98-123">![Aplicación BizTalkManagementService](../core/media/biztalkmanagementservice-apppool.png)</span><span class="sxs-lookup"><span data-stu-id="96c98-123">![BizTalkManagementService application](../core/media/biztalkmanagementservice-apppool.png)</span></span>

4. <span data-ttu-id="96c98-124">Para confirmar que funciona, vaya a `http://localhost/BizTalkManagementService/swagger`.</span><span class="sxs-lookup"><span data-stu-id="96c98-124">To confirm it’s working, browse to `http://localhost/BizTalkManagementService/swagger`.</span></span> <span data-ttu-id="96c98-125">Si le pedirá que inicie sesión, inicie sesión con una cuenta que sea miembro de la domain\group que escribió en el paso anterior (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`).</span><span class="sxs-lookup"><span data-stu-id="96c98-125">If you are prompted to sign-in, sign in with an account that is member of the domain\group you entered in the previous step (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`).</span></span> 

> [!WARNING]
> <span data-ttu-id="96c98-126">La aplicación BizTalkManagementService en IIS usa un archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="96c98-126">The BizTalkManagementService application in IIS uses a web.config file.</span></span> <span data-ttu-id="96c98-127">Elementos dentro de web.config **distinguen mayúsculas de minúsculas**.</span><span class="sxs-lookup"><span data-stu-id="96c98-127">Elements within web.config **are case sensitive**.</span></span> <span data-ttu-id="96c98-128">Por lo que al ejecutar el script de Windows PowerShell, asegúrese de escribir las mayúsculas y minúsculas correctas para `-AuthorizationRoles` valor.</span><span class="sxs-lookup"><span data-stu-id="96c98-128">So when you execute the Windows PowerShell script, be sure to enter the correct case for `-AuthorizationRoles` value.</span></span> <span data-ttu-id="96c98-129">Si no está seguro del caso, aquí es una manera fácil de averiguar:</span><span class="sxs-lookup"><span data-stu-id="96c98-129">If you’re not sure of the case, here’s an easy way to find out:</span></span> 
> 
> 1. <span data-ttu-id="96c98-130">Abra **administración de equipos**y expanda **usuarios y grupos locales**.</span><span class="sxs-lookup"><span data-stu-id="96c98-130">Open **Computer Management**, and expand **Local Users and Groups**.</span></span>
> 2. <span data-ttu-id="96c98-131">Seleccione **grupos**y desplácese hacia abajo hasta la **SQLServer...**</span><span class="sxs-lookup"><span data-stu-id="96c98-131">Select **Groups**, and scroll down to the **SQLServer…**</span></span> <span data-ttu-id="96c98-132">grupos.</span><span class="sxs-lookup"><span data-stu-id="96c98-132">groups.</span></span> 
> 3. <span data-ttu-id="96c98-133">En el ejemplo siguiente, observe **BOOTCAMPBTS2016** está en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="96c98-133">In the following example, notice **BOOTCAMPBTS2016** is in all caps.</span></span> <span data-ttu-id="96c98-134">Si ve todo en mayúsculas, a continuación, escriba el nombre del equipo en todo en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="96c98-134">If you see all caps, then enter the computer name in all caps.</span></span> 
> 
> ![Nombre del equipo está en mayúsculas](../core/media/groups-case.png)

<span data-ttu-id="96c98-136">Ahora que las API de REST se exponen a través de IIS, puede obtener acceso y ejecutadas por otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="96c98-136">Now that the REST APIs are exposed through IIS, they can be accessed and executed by other applications.</span></span> <span data-ttu-id="96c98-137">[Referencia de API de REST de paquete de características](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016) enumera las API.</span><span class="sxs-lookup"><span data-stu-id="96c98-137">[Feature Pack REST API reference](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016) lists the APIs.</span></span>

<span data-ttu-id="96c98-138">Puede cambiar quién tiene acceso mediante la actualización manualmente el **web.config** archivo, que se encuentra en la carpeta raíz de la aplicación de administración.</span><span class="sxs-lookup"><span data-stu-id="96c98-138">You can change who has access by manually updating the **web.config** file, which is in the root folder of the management application.</span></span> <span data-ttu-id="96c98-139">Por ejemplo, utilice los procedimientos siguientes para permitir que cualquier persona acceso a swagger de salida:</span><span class="sxs-lookup"><span data-stu-id="96c98-139">For example, use the following to allow anyone access to the swagger output:</span></span> 

```
<authorization>
   <allow users="*" />
</authorization>
```

## <a name="step-2-test-the-apis"></a><span data-ttu-id="96c98-140">Paso 2: Probar las API</span><span class="sxs-lookup"><span data-stu-id="96c98-140">Step 2: Test the APIs</span></span>

1. <span data-ttu-id="96c98-141">En el servidor BizTalk Server, vaya a `http://localhost/BizTalkManagementService/swagger`.</span><span class="sxs-lookup"><span data-stu-id="96c98-141">On the BizTalk Server, browse to `http://localhost/BizTalkManagementService/swagger`.</span></span>

2. <span data-ttu-id="96c98-142">Desplácese a **Hosts**y seleccione **mostrar u ocultar**.</span><span class="sxs-lookup"><span data-stu-id="96c98-142">Scroll to **Hosts**, and select **Show/Hide**.</span></span> <span data-ttu-id="96c98-143">Hay un comando GET; Haga clic en esta fila:</span><span class="sxs-lookup"><span data-stu-id="96c98-143">There is a GET command; click this row:</span></span>  
<span data-ttu-id="96c98-144">![OBTENER todos los hosts](../core/media/managment-rest-apis-hosts-get.png)</span><span class="sxs-lookup"><span data-stu-id="96c98-144">![GET all hosts](../core/media/managment-rest-apis-hosts-get.png)</span></span>

3. <span data-ttu-id="96c98-145">Muestra los detalles.</span><span class="sxs-lookup"><span data-stu-id="96c98-145">It shows the details.</span></span> <span data-ttu-id="96c98-146">Seleccione **Pruébelo**:</span><span class="sxs-lookup"><span data-stu-id="96c98-146">Select **Try it out**:</span></span>  
<span data-ttu-id="96c98-147">![Pruébelo](../core/media/managment-rest-apis-hosts-tryitout.png)</span><span class="sxs-lookup"><span data-stu-id="96c98-147">![Try it out](../core/media/managment-rest-apis-hosts-tryitout.png)</span></span>

4. <span data-ttu-id="96c98-148">El cuerpo de respuesta devuelve todos los hosts:</span><span class="sxs-lookup"><span data-stu-id="96c98-148">The Response Body returns all the hosts:</span></span>  
![Respuestas](../core/media/managment-rest-apis-hosts-response.png)

> [!NOTE]
> <span data-ttu-id="96c98-150">Si examina `http://localhost/BizTalkManagementService`, obtendrá un error 500.</span><span class="sxs-lookup"><span data-stu-id="96c98-150">If you browse to `http://localhost/BizTalkManagementService`, you should get a 500 error.</span></span> <span data-ttu-id="96c98-151">Eso es bueno.</span><span class="sxs-lookup"><span data-stu-id="96c98-151">That’s a good thing.</span></span> <span data-ttu-id="96c98-152">Basta con agregar `/swagger` al final de la dirección URL y verá la API de REST disponibles.</span><span class="sxs-lookup"><span data-stu-id="96c98-152">Just add `/swagger` to the end of URL, and you’ll see the available REST APIs.</span></span> 


## <a name="see-also"></a><span data-ttu-id="96c98-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="96c98-153">See also</span></span>
 [<span data-ttu-id="96c98-154">Configuración del Feature Pack</span><span class="sxs-lookup"><span data-stu-id="96c98-154">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)