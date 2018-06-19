---
title: Cómo modificar las propiedades de grupo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, groups
- configuring, groups
- groups, configuring
- managing [groups], properties
- groups, modifying
- managing [groups], modifying
- groups, properties
ms.assetid: 59e0853d-81b0-43f9-85bf-099868e25fad
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a191011b6824086e26c72ce5e5a182a167ca0e37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254868"
---
# <a name="how-to-modify-group-properties"></a><span data-ttu-id="9d9ae-102">Cómo modificar propiedades de grupo</span><span class="sxs-lookup"><span data-stu-id="9d9ae-102">How to Modify Group Properties</span></span>
<span data-ttu-id="9d9ae-103">Puede utilizar este procedimiento para configurar propiedades globales para el grupo de BizTalk Server, de manera que se pueda seleccionar un certificado de firma, modificar el intervalo de actualización de la caché y determinar cómo controlará BizTalk Server los mensajes de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-103">You can use this procedure to configure global properties for your BizTalk Server group so that you can select a signing certificate, modify the cache refresh interval, and determine how BizTalk Server will handle large messages.</span></span> <span data-ttu-id="9d9ae-104">Para obtener más información acerca de las propiedades de grupo de BizTalk Server, vea [grupos de BizTalk](../core/biztalk-groups.md).</span><span class="sxs-lookup"><span data-stu-id="9d9ae-104">For more information about BizTalk Server group properties, see [BizTalk Groups](../core/biztalk-groups.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9d9ae-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9d9ae-105">Prerequisites</span></span>  
 <span data-ttu-id="9d9ae-106">Para realizar este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-106">To perform this procedure, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-group-properties"></a><span data-ttu-id="9d9ae-107">Para configurar propiedades de grupo BizTalk</span><span class="sxs-lookup"><span data-stu-id="9d9ae-107">To configure BizTalk group properties</span></span>  
  
1.  <span data-ttu-id="9d9ae-108">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-108">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9d9ae-109">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **grupo de BizTalk**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-109">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, right-click **BizTalk Group**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="9d9ae-110">En el **propiedades del grupo de** cuadro de diálogo, en la **General** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d9ae-110">In the **Group Properties** dialog box, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="9d9ae-111">Use</span><span class="sxs-lookup"><span data-stu-id="9d9ae-111">Use this</span></span>|<span data-ttu-id="9d9ae-112">Para</span><span class="sxs-lookup"><span data-stu-id="9d9ae-112">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9d9ae-113">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9d9ae-113">**Name**</span></span>|<span data-ttu-id="9d9ae-114">Escribir el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-114">Type the group name.</span></span> <span data-ttu-id="9d9ae-115">El nombre del grupo no puede superar los 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-115">The group name cannot exceed 128 characters in length.</span></span> <span data-ttu-id="9d9ae-116">El nombre de este cuadro aparece junto a la **grupo** nodo en el árbol de consola, junto con el nombre del servidor y el nombre de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-116">The name in this box appears next to the **Group** node in the console tree, along with the server name and the BizTalk Management database name.</span></span>|  
    |<span data-ttu-id="9d9ae-117">**Server**</span><span class="sxs-lookup"><span data-stu-id="9d9ae-117">**Server**</span></span>|<span data-ttu-id="9d9ae-118">Mostrar el servidor en el que se almacena físicamente la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-118">Displays the server on which the BizTalk Management database is physically stored.</span></span>|  
    |<span data-ttu-id="9d9ae-119">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="9d9ae-119">**Database**</span></span>|<span data-ttu-id="9d9ae-120">Mostrar la base de datos de administración de BizTalk en la que se almacena toda la configuración de este grupo.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-120">Displays the BizTalk Management database on which all configuration settings for this group are stored.</span></span>|  
    |<span data-ttu-id="9d9ae-121">**Nombre del servidor de SSO**</span><span class="sxs-lookup"><span data-stu-id="9d9ae-121">**SSO Server name**</span></span>|<span data-ttu-id="9d9ae-122">Escribir el nombre del servidor de inicio de sesión único (SSO) empresarial que utilizará este equipo para almacenar la información específica de adaptador, así como para obtener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-122">Type the name of the Enterprise Single Sign-On (SSO) server that this computer will use to store and access adapter-specific information.</span></span> <span data-ttu-id="9d9ae-123">Éste es el nombre del servidor de SSO utilizado para establecer la conexión con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-123">This is the name of the SSO server used to connect to the SSO database.</span></span>|  
    |<span data-ttu-id="9d9ae-124">**Grupo de administradores de BizTalk**</span><span class="sxs-lookup"><span data-stu-id="9d9ae-124">**BizTalk Administrator Group**</span></span>|<span data-ttu-id="9d9ae-125">Mostrar el nombre del grupo de administradores que tiene derechos para administrar el entorno de BizTalk Server después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-125">Displays the name of the administrators group that has rights to manage the BizTalk Server environment after installation.</span></span>|  
    |<span data-ttu-id="9d9ae-126">**Grupo de operadores de BizTalk**</span><span class="sxs-lookup"><span data-stu-id="9d9ae-126">**BizTalk Operators Group**</span></span>|<span data-ttu-id="9d9ae-127">Muestra el nombre del grupo de operadores que no tiene derechos para ver la configuración, ejecutar consultas y realizar mantenimiento del equipo y la supervisión de aplicaciones básica.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-127">Displays the name of the operators group that has rights to view configuration, run queries, and perform computer maintenance and basic application monitoring.</span></span>|  
    |<span data-ttu-id="9d9ae-128">**Operadores de B2B de BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="9d9ae-128">**BizTalk Server B2B Operators**</span></span>|<span data-ttu-id="9d9ae-129">Muestra el nombre del grupo de operadores B2B.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-129">Displays the name of the B2B operators group.</span></span>|  
  
4.  <span data-ttu-id="9d9ae-130">En el **bases de datos** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d9ae-130">On the **Databases** tab, do the following:</span></span>  
  
    |<span data-ttu-id="9d9ae-131">Use</span><span class="sxs-lookup"><span data-stu-id="9d9ae-131">Use this</span></span>|<span data-ttu-id="9d9ae-132">Para</span><span class="sxs-lookup"><span data-stu-id="9d9ae-132">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9d9ae-133">**Bases de datos**</span><span class="sxs-lookup"><span data-stu-id="9d9ae-133">**Databases**</span></span>|<span data-ttu-id="9d9ae-134">Mostrar los nombres de todas las bases de datos en la aplicación y de todos los servidores en los que residen, tal como se especificó durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-134">Displays the names of all databases in the application and the servers on which they reside, as specified during configuration.</span></span>|  
  
5.  <span data-ttu-id="9d9ae-135">En el **certificado** ficha, realice lo siguiente y, a continuación, haga clic en **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="9d9ae-135">On the **Certificate** tab, do the following, and then click **OK**:</span></span>  
  
    |<span data-ttu-id="9d9ae-136">Use</span><span class="sxs-lookup"><span data-stu-id="9d9ae-136">Use this</span></span>|<span data-ttu-id="9d9ae-137">Para</span><span class="sxs-lookup"><span data-stu-id="9d9ae-137">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9d9ae-138">**Nombre común**</span><span class="sxs-lookup"><span data-stu-id="9d9ae-138">**Common Name**</span></span>|<span data-ttu-id="9d9ae-139">Ver una descripción del certificado seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-139">Displays a description of the selected certificate.</span></span>|  
    |<span data-ttu-id="9d9ae-140">**Huella digital**</span><span class="sxs-lookup"><span data-stu-id="9d9ae-140">**Thumbprint**</span></span>|<span data-ttu-id="9d9ae-141">Mostrar la huella digital del certificado de clave privada que se utiliza para firmar digitalmente los mensajes de salida de este grupo.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-141">Displays the thumbprint of the private key certificate that is used to digitally sign outbound messages from this group.</span></span> <span data-ttu-id="9d9ae-142">La huella digital del certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal (un número entre 0 y 9) o una letra de la A F.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-142">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit (a number from 0 through 9 or a letter from A through F).</span></span>|  
    |<span data-ttu-id="9d9ae-143">**Quitar certificado**</span><span class="sxs-lookup"><span data-stu-id="9d9ae-143">**Remove certificate**</span></span>|<span data-ttu-id="9d9ae-144">Quitar el certificado que aparece en pantalla.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-144">Click to remove the displayed certificate.</span></span>|  
    |<span data-ttu-id="9d9ae-145">**Examinar**</span><span class="sxs-lookup"><span data-stu-id="9d9ae-145">**Browse**</span></span>|<span data-ttu-id="9d9ae-146">Haga clic para mostrar la **Seleccionar certificado** cuadro de diálogo donde seleccionar el certificado de firma para el usuario actual o el almacén personal que desea usar con el grupo.</span><span class="sxs-lookup"><span data-stu-id="9d9ae-146">Click to display the **Select Certificate** dialog box, where you select the signature certificate for the current user or personal store you want to use with the group.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d9ae-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d9ae-147">See Also</span></span>  
 <span data-ttu-id="9d9ae-148">[Administración de grupos](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="9d9ae-148">[Managing Groups](../core/managing-groups.md) </span></span>  
 <span data-ttu-id="9d9ae-149">[Grupos de BizTalk](../core/biztalk-groups.md) </span><span class="sxs-lookup"><span data-stu-id="9d9ae-149">[BizTalk Groups](../core/biztalk-groups.md) </span></span>  
 <span data-ttu-id="9d9ae-150">[Cómo agregar un servidor a un grupo](../core/how-to-add-a-server-to-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="9d9ae-150">[How to Add a Server to a Group](../core/how-to-add-a-server-to-a-group.md) </span></span>  
 <span data-ttu-id="9d9ae-151">[Cómo mover un servidor de un grupo a otro](../core/how-to-move-a-server-from-one-group-to-another.md) </span><span class="sxs-lookup"><span data-stu-id="9d9ae-151">[How to Move a Server from One Group to Another](../core/how-to-move-a-server-from-one-group-to-another.md) </span></span>  
 [<span data-ttu-id="9d9ae-152">Cómo quitar un servidor de un grupo</span><span class="sxs-lookup"><span data-stu-id="9d9ae-152">How to Remove a Server from a Group</span></span>](../core/how-to-remove-a-server-from-a-group.md)