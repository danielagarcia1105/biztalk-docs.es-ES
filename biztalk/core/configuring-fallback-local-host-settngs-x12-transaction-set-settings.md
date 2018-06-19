---
title: Configurar configuración errónea del Host Local de reserva (configuración de conjunto de transacciones de X12) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68511199-a7ed-45b3-807d-70378b2c6ebb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fa9e1fcc8bf1764a16142d38058e14878341fdc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233396"
---
# <a name="configuring-fallback-local-host-settngs-x12-transaction-set-settings"></a><span data-ttu-id="99ef0-102">Configuración de las opciones de host local de reserva (configuración del conjunto de transacciones de X12)</span><span class="sxs-lookup"><span data-stu-id="99ef0-102">Configuring Fallback Local Host Settngs (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="99ef0-103">Para procesar un intercambio entrante, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe determinar el esquema que necesita usar en el procesamiento y la validación del intercambio.</span><span class="sxs-lookup"><span data-stu-id="99ef0-103">To process an incoming interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must determine the schema that it needs to use in processing and validating the interchange.</span></span> <span data-ttu-id="99ef0-104">Esto consiste en determinar el espacio de nombres de destino asociado al esquema y el esquema que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="99ef0-104">This consists of determining the target namespace associated with the schema, and determining the schema to be used.</span></span> <span data-ttu-id="99ef0-105">En esta página del contrato de reserva, especifique el espacio de nombres de destino de reserva.</span><span class="sxs-lookup"><span data-stu-id="99ef0-105">In this page of the fallback agreement, you specify the fallback target namespace.</span></span> <span data-ttu-id="99ef0-106">Cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determina el esquema se describe en [resolución de acuerdos, detección de esquemas y autorización para los mensajes de EDI recibidos](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span><span class="sxs-lookup"><span data-stu-id="99ef0-106">How [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determines the schema is described in [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99ef0-107">Este tema se aplica también a valores de configuración relacionados con HIPAA.</span><span class="sxs-lookup"><span data-stu-id="99ef0-107">This topic applies also to HIPAA-related settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="99ef0-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="99ef0-108">Prerequisites</span></span>  
 <span data-ttu-id="99ef0-109">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99ef0-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a><span data-ttu-id="99ef0-110">Para configurar el host local para conjuntos de transacciones</span><span class="sxs-lookup"><span data-stu-id="99ef0-110">To configure local host settings for transaction sets</span></span>  
  
1.  <span data-ttu-id="99ef0-111">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva**.</span><span class="sxs-lookup"><span data-stu-id="99ef0-111">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="99ef0-112">En el **X12 configuración de reserva** cuadro de diálogo la **X12 páginas del acuerdo** , bajo la **configuración del conjunto de transacciones** sección, haga clic en **configuración de Host Local** .</span><span class="sxs-lookup"><span data-stu-id="99ef0-112">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Transaction Set Settings** section, click **Local Host Settings**.</span></span>  
  
3.  <span data-ttu-id="99ef0-113">Seleccione **convertir formato decimal implícito Nn a valor numérico 10 base** para convertir un número EDI especificado con el formato Nn en un valor numérico de base 10 en el XML intermedio en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="99ef0-113">Select **Convert implied decimal format Nn to base 10 numeric value** to convert an EDI number that is specified with the format Nn into a base-10 numeric value in the intermediate XML in BizTalk Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99ef0-114">Después de esta conversión, puede haber errores en la validación de la longitud del XML intermedio.</span><span class="sxs-lookup"><span data-stu-id="99ef0-114">After this conversion, the intermediate XML may fail length validation.</span></span> <span data-ttu-id="99ef0-115">Ello se debe a que el número en formato numérico de base 10 incluye un decimal, lo que conlleva que su longitud sea superior en uno al número en formato Nn.</span><span class="sxs-lookup"><span data-stu-id="99ef0-115">This occurs because the number in the base-10 numeric format includes a decimal, making its length one greater than the number in Nn format.</span></span> <span data-ttu-id="99ef0-116">Puede resolver este problema, agregue un valor de **1** en el valor de longitud mínima o máxima.</span><span class="sxs-lookup"><span data-stu-id="99ef0-116">You can resolve this issue by adding a value of **1** to the minimum/maximum length value.</span></span>  
  
4.  <span data-ttu-id="99ef0-117">Seleccione **crear etiquetas XML vacías para los separadores finales** para que el remitente del intercambio incluya etiquetas XML vacías para separadores finales.</span><span class="sxs-lookup"><span data-stu-id="99ef0-117">Select **Create empty XML tags for trailing separators** to have the interchange sender include empty XML tags for trailing separators.</span></span>  
  
5.  <span data-ttu-id="99ef0-118">Para **Target Namespace**, escriba (o seleccione en la lista desplegable) el espacio de nombres de destino que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se utiliza para determinar el esquema que se va a procesar el mensaje recibido.</span><span class="sxs-lookup"><span data-stu-id="99ef0-118">For **Target Namespace**, enter (or select from the drop-down list) the target namespace that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses to determine the schema to process the received message with.</span></span>  
  
6.  <span data-ttu-id="99ef0-119">Haga clic en **aplicar** para aceptar los cambios o haga clic en **Aceptar** para introducir y validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="99ef0-119">Click **Apply** to accept the changes, or click **OK** to enter and validate the changes, and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ef0-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="99ef0-120">See Also</span></span>  
 [<span data-ttu-id="99ef0-121">Configurar X12 configuración propiedades del acuerdo de reserva para transacciones</span><span class="sxs-lookup"><span data-stu-id="99ef0-121">Configuring X12 Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)