---
title: "Configuración de HTTP para MDN | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c877e85-7887-43a9-9fd4-0853b573213f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f74ba2eaf11e8beed3e28d10beb9f95b2f0f6194
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-http-settings-for-mdns"></a><span data-ttu-id="8e129-102">Configuración de valores HTTP para MDNs</span><span class="sxs-lookup"><span data-stu-id="8e129-102">Configuring HTTP Settings for MDNs</span></span>
<span data-ttu-id="8e129-103">Como parte de la configuración HTTP relacionada con MDN, puede especificar las propiedades que espera el servidor web que recibe los MDN.</span><span class="sxs-lookup"><span data-stu-id="8e129-103">As part of MDN-related HTTP settings, you can specify the properties expected by the Web server that receives the MDNs.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8e129-104">Todas las propiedades se deshabilitan en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.</span><span class="sxs-lookup"><span data-stu-id="8e129-104">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="8e129-105">Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad.</span><span class="sxs-lookup"><span data-stu-id="8e129-105">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="8e129-106">Por ejemplo, si crea dos entidades, entidad A y entidad B y para la entidad A ha desactivado la casilla de verificación, la lista de propiedades anterior se deshabilita en el **entidad A -> B entidad** ficha de acuerdo unidireccional.</span><span class="sxs-lookup"><span data-stu-id="8e129-106">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8e129-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8e129-107">Prerequisites</span></span>  
 <span data-ttu-id="8e129-108">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e129-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-mdn-related-http-settings"></a><span data-ttu-id="8e129-109">Para configurar los valores de HTTP relacionados con MDN</span><span class="sxs-lookup"><span data-stu-id="8e129-109">To configure MDN-related HTTP settings</span></span>  
  
1.  <span data-ttu-id="8e129-110">Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md).</span><span class="sxs-lookup"><span data-stu-id="8e129-110">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="8e129-111">Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8e129-111">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="8e129-112">En una ficha de acuerdo unidireccional, bajo **configuración de Host Local** sección, haga clic en **configuración HTTP para MDN**.</span><span class="sxs-lookup"><span data-stu-id="8e129-112">On a one-way agreement tab, under **Local Host Settings** section, click **HTTP Settings for MDNs**.</span></span>  
  
3.  <span data-ttu-id="8e129-113">Seleccione el **error de coincidencia de nombre del certificado SSL omitir** aceptarán casilla de verificación para asegurarse de que si el nombre del servidor no coincide con el nombre del servidor que se generó el certificado SSL, debe tener una conexión SSL.</span><span class="sxs-lookup"><span data-stu-id="8e129-113">Select the **Ignore SSL Certificate Name mismatch** check box to ensure that if the server name does not match the server name that the SSL certificate was generated for, the SSL connection would still be accepted.</span></span>  
  
4.  <span data-ttu-id="8e129-114">Haga clic en **expect de HTTP 100 continue** para establecer el encabezado Expect de HTTP a 100-continue, que especifica que los datos enviados no se incluirán en la solicitud HTTP inicial, pero espera a que el servidor solicite el contenido.</span><span class="sxs-lookup"><span data-stu-id="8e129-114">Click **HTTP expect 100 continue** to set the HTTP Expect header to 100-continue, which specifies that the posted data not be included in the initial HTTP request, but waits for the server to request the content.</span></span>  
  
5.  <span data-ttu-id="8e129-115">Haga clic en **activa la conexión HTTP mantener** para solicitar que una conexión HTTP se mantenga activa una vez completado un ciclo de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="8e129-115">Click **Keep HTTP connection alive** to request that an HTTP connection be kept alive after a request and response cycle has been completed.</span></span>  
  
6.  <span data-ttu-id="8e129-116">Haga clic en **expandir encabezados HTTP** para desplegar el encabezado content-type HTTP en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="8e129-116">Click **Unfold HTTP headers** to unfold the HTTP content-type header into a single line.</span></span>  
  
7.  <span data-ttu-id="8e129-117">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8e129-117">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e129-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e129-118">See Also</span></span>  
 [<span data-ttu-id="8e129-119">Configuración del Host Local (AS2)</span><span class="sxs-lookup"><span data-stu-id="8e129-119">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)