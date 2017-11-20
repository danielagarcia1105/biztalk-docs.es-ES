---
title: "Configuración de Host Local de reserva (configuración del conjunto de transacciones EDIFACT) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0142b3fc-009f-4da5-b34d-dddf4fb96e0f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 931db62edda264a6fff0ddb422bd41b243cd29ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-local-host-settings-edifact-transaction-set-settings"></a><span data-ttu-id="ee9db-102">Configuración de las opciones de host local de reserva (configuración del conjunto de transacciones de EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="ee9db-102">Configuring Fallback Local Host Settings (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="ee9db-103">Para procesar un intercambio entrante, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe determinar el esquema que necesita usar en el procesamiento y la validación del intercambio.</span><span class="sxs-lookup"><span data-stu-id="ee9db-103">To process an incoming interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must determine the schema that it needs to use in processing and validating the interchange.</span></span> <span data-ttu-id="ee9db-104">Esto consiste en determinar el espacio de nombres de destino asociado al esquema y el esquema que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="ee9db-104">This consists of determining the target namespace associated with the schema, and determining the schema to be used.</span></span> <span data-ttu-id="ee9db-105">En esta página de acuerdo de reserva, especifique las propiedades que se van a usar en la determinación del espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="ee9db-105">In this page of fallback agreement, you enter the properties to be used in determining the target namespace.</span></span> <span data-ttu-id="ee9db-106">Cómo BizTalk Server determina el esquema se describe en [resolución de acuerdos, detección de esquemas y autorización para los mensajes de EDI recibidos](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span><span class="sxs-lookup"><span data-stu-id="ee9db-106">How BizTalk Server determines the schema is described in [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ee9db-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ee9db-107">Prerequisites</span></span>  
 <span data-ttu-id="ee9db-108">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee9db-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a><span data-ttu-id="ee9db-109">Para configurar el host local para conjuntos de transacciones</span><span class="sxs-lookup"><span data-stu-id="ee9db-109">To configure local host settings for transaction sets</span></span>  
  
1.  <span data-ttu-id="ee9db-110">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.</span><span class="sxs-lookup"><span data-stu-id="ee9db-110">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="ee9db-111">En el **configuración de reserva de EDIFACT** cuadro de diálogo la **páginas del acuerdo EDIFACT** , bajo la **configuración del conjunto de transacciones** sección, haga clic en **Host Local Configuración de**.</span><span class="sxs-lookup"><span data-stu-id="ee9db-111">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Transaction Set Settings** section, click **Local Host Settings**.</span></span>  
  
3.  <span data-ttu-id="ee9db-112">Seleccione **crear etiquetas XML vacías para los separadores finales** para que el remitente del intercambio incluya etiquetas XML vacías para separadores finales.</span><span class="sxs-lookup"><span data-stu-id="ee9db-112">Select **Create empty XML tags for trailing separators** to have the interchange sender include empty XML tags for trailing separators.</span></span>  
  
4.  <span data-ttu-id="ee9db-113">Seleccione **usar punto (.) como separador decimal** para habilitar el servidor BizTalk Server incluyen un punto (.) en el mensaje XML creado a partir de un intercambio que contiene un número decimal.</span><span class="sxs-lookup"><span data-stu-id="ee9db-113">Select **Use Dot (.) as decimal separator** to enable BizTalk Server include a dot (.) in the XML message created out of an interchange that contains a decimal number.</span></span>  
  
5.  <span data-ttu-id="ee9db-114">Para **Target Namespace**, escriba (o seleccione en la lista desplegable) el espacio de nombres de destino que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utilizará para determinar el esquema que se va a procesar el mensaje recibido</span><span class="sxs-lookup"><span data-stu-id="ee9db-114">For **Target Namespace**, enter (or select from the drop-down list) the target namespace that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to determine the schema to process the received message with</span></span>  
  
6.  <span data-ttu-id="ee9db-115">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ee9db-115">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee9db-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee9db-116">See Also</span></span>  
 [<span data-ttu-id="ee9db-117">Configurar la configuración de propiedades de acuerdo de reserva de EDIFACT para la transacción</span><span class="sxs-lookup"><span data-stu-id="ee9db-117">Configuring EDIFACT Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)