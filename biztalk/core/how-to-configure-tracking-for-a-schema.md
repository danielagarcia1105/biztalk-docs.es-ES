---
title: Cómo configurar el seguimiento de un esquema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, configuring
- managing [schemas], configuring
- configuring [HAT tracking], schemas
- configuring, schemas
- configuring, tracking
- HAT, schemas
- managing [schemas], tracking
- schemas, tracking
- tracking, configuring
- tracking, schemas
ms.assetid: b5f69c98-8824-43b1-8f21-d84b60ac5431
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daef2bb1b118388897f98b6c2fa885b7fed4bbc0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000333"
---
# <a name="how-to-configure-tracking-for-a-schema"></a><span data-ttu-id="9a416-102">Cómo configurar el seguimiento de un esquema</span><span class="sxs-lookup"><span data-stu-id="9a416-102">How to Configure Tracking for a Schema</span></span>
<span data-ttu-id="9a416-103">En este tema se describe cómo usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar el seguimiento de un esquema.</span><span class="sxs-lookup"><span data-stu-id="9a416-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a schema.</span></span> <span data-ttu-id="9a416-104">Para configurar el seguimiento, especifique las propiedades de los mensajes que desee ver en las vistas de consulta de la página Concentrador de grupo de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a416-104">To configure tracking, you specify the properties of the messages that you want to view in the query views of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console Group Hub page.</span></span>  
  
 <span data-ttu-id="9a416-105">Para obtener más información sobre la creación y uso de consultas, vea [mediante la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="9a416-105">For more information about creating and using queries, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span> <span data-ttu-id="9a416-106">Para obtener más información acerca de la instancia de servicio y eventos de mensaje seguimiento de las características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [Ver mensaje realiza el seguimiento y datos de instancia](../core/viewing-tracked-message-and-instance-data.md).</span><span class="sxs-lookup"><span data-stu-id="9a416-106">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9a416-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9a416-107">Prerequisites</span></span>  
 <span data-ttu-id="9a416-108">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9a416-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="9a416-109">Si desea ver sólo opciones de seguimiento, puede iniciar la sesión como un miembro del grupo de operadores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9a416-109">To you want to view tracking options only, you can be logged on as a member of the BizTalk Server Operators group.</span></span> <span data-ttu-id="9a416-110">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="9a416-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-schema"></a><span data-ttu-id="9a416-111">Para configurar el seguimiento de un esquema</span><span class="sxs-lookup"><span data-stu-id="9a416-111">To configure tracking for a schema</span></span>  
  
1. <span data-ttu-id="9a416-112">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="9a416-112">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="9a416-113">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene el esquema para el que desea configurar el seguimiento y, a continuación, expanda la aplicación que contiene el esquema.</span><span class="sxs-lookup"><span data-stu-id="9a416-113">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the schema for which you want to configure tracking, and then expand the application containing the schema.</span></span>  
  
3. <span data-ttu-id="9a416-114">Haga clic en **esquemas**, haga clic en el esquema y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9a416-114">Click **Schemas**, right-click the schema, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="9a416-115">En el panel izquierdo, haga clic en **seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="9a416-115">In the left pane, click **Tracking**.</span></span>  
  
5. <span data-ttu-id="9a416-116">Realice una de las siguientes opciones para especificar qué propiedades que se usará para el seguimiento de mensajes y, a continuación, haga clic en **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="9a416-116">Do one of the following to specify which properties to use for tracking messages, and then click **OK**:</span></span>  
  
   -   <span data-ttu-id="9a416-117">Seleccione el **seleccionar todas las propiedades de mensaje** casilla de verificación para utilizar todas las propiedades enumeradas.</span><span class="sxs-lookup"><span data-stu-id="9a416-117">Select the **Select all message properties** check box to use all the listed properties.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="9a416-118">Esta casilla solo está disponible para los esquemas que contienen propiedades promocionadas.</span><span class="sxs-lookup"><span data-stu-id="9a416-118">This check box is available only for schemas that contain promoted properties.</span></span>  
  
   -   <span data-ttu-id="9a416-119">Seleccione la casilla de verificación para cada una de las propiedades que quiera utilizar.</span><span class="sxs-lookup"><span data-stu-id="9a416-119">Select the check box of each property that you want to use.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="9a416-120">Esto solo está disponible para los esquemas que contienen propiedades promocionadas.</span><span class="sxs-lookup"><span data-stu-id="9a416-120">This is available only for schemas that contain promoted properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a416-121">Debería seleccionar sólo las opciones que necesita ya que el seguimiento de mensajes produce una sobrecarga de rendimiento y almacenamiento para su sistema.</span><span class="sxs-lookup"><span data-stu-id="9a416-121">You should select only the options you need, as tracking messages creates performance and storage overhead for your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a416-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a416-122">See Also</span></span>  
 [<span data-ttu-id="9a416-123">Administración de esquemas</span><span class="sxs-lookup"><span data-stu-id="9a416-123">Managing Schemas</span></span>](../core/managing-schemas.md)