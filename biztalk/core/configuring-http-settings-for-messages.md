---
title: "Configuración de HTTP para mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ed400f1-561d-4812-adf1-20e4300fd048
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d15ebb5ff5be6678c4dc2aee3f9333f36c75c89f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-http-settings-for-messages"></a><span data-ttu-id="a1156-102">Configuración de HTTP para mensajes</span><span class="sxs-lookup"><span data-stu-id="a1156-102">Configuring HTTP Settings for Messages</span></span>
<span data-ttu-id="a1156-103">Como parte de la configuración HTTP relacionada con los mensajes, puede especificar las propiedades que espera el servidor web que recibe mensajes AS2.</span><span class="sxs-lookup"><span data-stu-id="a1156-103">As part of message-related HTTP settings, you can specify the properties expected by the Web server that receives AS2 messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a1156-104">Ninguna propiedad se deshabilita en **entidad A -> B entidad** ficha de acuerdo unidireccional si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación para la entidad A. Sin embargo, se deshabilitan todas las propiedades en la misma página en la **parte B -> parte A** ficha si ha seleccionado la casilla de verificación al crear la entidad A.</span><span class="sxs-lookup"><span data-stu-id="a1156-104">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a1156-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a1156-105">Prerequisites</span></span>  
 <span data-ttu-id="a1156-106">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1156-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-message-related-http-settings"></a><span data-ttu-id="a1156-107">Para configurar los valores de HTTP relacionados con mensajes</span><span class="sxs-lookup"><span data-stu-id="a1156-107">To configure message-related HTTP settings</span></span>  
  
1.  <span data-ttu-id="a1156-108">Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md).</span><span class="sxs-lookup"><span data-stu-id="a1156-108">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="a1156-109">Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a1156-109">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a1156-110">En una ficha de acuerdo unidireccional, bajo **configuración de Host Local** sección, haga clic en **configuración HTTP para mensajes**.</span><span class="sxs-lookup"><span data-stu-id="a1156-110">On a one-way agreement tab, under **Local Host Settings** section, click **HTTP Settings for Messages**.</span></span>  
  
3.  <span data-ttu-id="a1156-111">Seleccione el **error de coincidencia de nombre del certificado SSL omitir** aceptarán casilla de verificación para asegurarse de que si el nombre del servidor no coincide con el nombre del servidor que se generó el certificado SSL, debe tener una conexión SSL.</span><span class="sxs-lookup"><span data-stu-id="a1156-111">Select the **Ignore SSL Certificate Name mismatch** check box to ensure that if the server name does not match the server name that the SSL certificate was generated for, the SSL connection would still be accepted.</span></span>  
  
4.  <span data-ttu-id="a1156-112">Haga clic en **expect de HTTP 100 continue** para establecer el encabezado Expect de HTTP a 100-continue, que especifica que los datos enviados no se incluirán en la solicitud HTTP inicial, pero espera a que el servidor solicite el contenido.</span><span class="sxs-lookup"><span data-stu-id="a1156-112">Click **HTTP expect 100 continue** to set the HTTP Expect header to 100-continue, which specifies that the posted data not be included in the initial HTTP request, but waits for the server to request the content.</span></span>  
  
5.  <span data-ttu-id="a1156-113">Haga clic en **activa la conexión HTTP mantener** para solicitar que una conexión HTTP se mantenga activa una vez completado un ciclo de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="a1156-113">Click **Keep HTTP connection alive** to request that an HTTP connection be kept alive after a request and response cycle has been completed.</span></span>  
  
6.  <span data-ttu-id="a1156-114">Haga clic en **expandir encabezados HTTP** para desplegar el encabezado content-type HTTP en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="a1156-114">Click **Unfold HTTP headers** to unfold the HTTP content-type header into a single line.</span></span>  
  
7.  <span data-ttu-id="a1156-115">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a1156-115">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1156-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1156-116">See Also</span></span>  
 [<span data-ttu-id="a1156-117">Configuración del Host Local (AS2)</span><span class="sxs-lookup"><span data-stu-id="a1156-117">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)