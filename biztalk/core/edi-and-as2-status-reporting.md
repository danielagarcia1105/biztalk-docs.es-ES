---
title: EDI y AS2 informes de estado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9e58b29-9be0-41d6-ad35-1aae28e1a784
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31b08fd8222cee0cb0f04750eedcb32d06c28820
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-and-as2-status-reporting"></a><span data-ttu-id="cc70f-102">Informes de estado de EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="cc70f-102">EDI and AS2 Status Reporting</span></span>
<span data-ttu-id="cc70f-103">Los informes de estado de EDI permiten que el personal de operaciones realice el seguimiento de las transmisiones EDI y AS2.</span><span class="sxs-lookup"><span data-stu-id="cc70f-103">EDI status reporting enables operations personnel to track the status of EDI and AS2 transmissions.</span></span> <span data-ttu-id="cc70f-104">Si están habilitados, los informes de estado proporcionan información completa sobre el estado de la transacción de intercambio de un documento, incluidos el intercambio y las confirmaciones correlacionadas.</span><span class="sxs-lookup"><span data-stu-id="cc70f-104">If enabled, status reports provide comprehensive status of a document exchange transaction, including an interchange and any acknowledgments correlated to the interchange.</span></span> <span data-ttu-id="cc70f-105">Estos informes proporcionan datos sobre el procesamiento de la recepción, la validación, el proceso por lotes y la confirmación de los mensajes EDI y AS2.</span><span class="sxs-lookup"><span data-stu-id="cc70f-105">These reports provide data on receipt, validation, batching, and acknowledgment processing of EDI and AS2 messages.</span></span>  
  
 <span data-ttu-id="cc70f-106">Se pueden usar para obtener el estado de los intercambios pendientes y sin confirmar, los intercambios completos, los escenarios de error o escenarios empresariales.</span><span class="sxs-lookup"><span data-stu-id="cc70f-106">You can use these reports to get the status of pending and unacknowledged interchanges, complete interchanges, error scenarios, or business scenarios.</span></span> <span data-ttu-id="cc70f-107">Estos informes permiten llevar a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cc70f-107">With these reports, you can do the following:</span></span>  
  
-   <span data-ttu-id="cc70f-108">Confirmar la recepción de intercambios</span><span class="sxs-lookup"><span data-stu-id="cc70f-108">Confirm the receipt of interchanges</span></span>  
  
-   <span data-ttu-id="cc70f-109">Enumerar intercambios salientes en espera de confirmación</span><span class="sxs-lookup"><span data-stu-id="cc70f-109">List outgoing interchanges awaiting acknowledgment</span></span>  
  
-   <span data-ttu-id="cc70f-110">Enumerar todos los intercambios rechazados recibidos</span><span class="sxs-lookup"><span data-stu-id="cc70f-110">List all rejected interchanges received</span></span>  
  
-   <span data-ttu-id="cc70f-111">Enumerar intercambios salientes que figuran como rechazados o aceptados parcialmente.</span><span class="sxs-lookup"><span data-stu-id="cc70f-111">List outgoing interchanges that are reported as rejected or partially accepted.</span></span>  
  
 <span data-ttu-id="cc70f-112">Los datos incluidos en los informes de estado se obtienen de los segmentos de control de intercambios, como ISA, TA1, GS, UNB y UNG (con la excepción del estado de confirmación funcional).</span><span class="sxs-lookup"><span data-stu-id="cc70f-112">Data included in the status reports is obtained from interchange control segments, such as ISA, TA1, GS, UNB, and UNG (with the exception of the Functional ACK status).</span></span>  
  
 <span data-ttu-id="cc70f-113">**Interfaz de usuario informes de estado**</span><span class="sxs-lookup"><span data-stu-id="cc70f-113">**Status Reporting UI**</span></span>  
  
 <span data-ttu-id="cc70f-114">Los informes de estado de EDI y AS2 están disponibles en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc70f-114">EDI and AS2 status reports are available from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="cc70f-115">Desde el **concentrador de grupo** página de la **grupo de BizTalk** nodo, dispone de vínculos al intercambio EDI y estado de confirmación correlacionado, estado del lote y mensaje AS2 y MDN correlacionado.</span><span class="sxs-lookup"><span data-stu-id="cc70f-115">From the **Group Hub** page of the **BizTalk Group** node, you have links to EDI interchange and correlated acknowledgment status, batch status, and AS2 message and correlated MDN status.</span></span> <span data-ttu-id="cc70f-116">Cada uno de estos informes proporciona una gama de parámetros de estado que pueden incluirse o excluirse de una expresión de consulta, lo que permite generar el informe de estado que necesite.</span><span class="sxs-lookup"><span data-stu-id="cc70f-116">Each of these reports provides a range of status parameters that you can include or exclude from a query expression, enabling you to build the status report that they need.</span></span>  
  
 <span data-ttu-id="cc70f-117">Además de ver el estado de un intercambio EDI, también se pueden ver los conjuntos de transacciones de un intercambio.</span><span class="sxs-lookup"><span data-stu-id="cc70f-117">In addition to seeing the status of an EDI interchange, you can also view the transaction sets in an interchange.</span></span> <span data-ttu-id="cc70f-118">Para ello, habilite el almacenamiento de cargas de mensajes en las tablas de EDI de la base de datos de seguimiento (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="cc70f-118">You do so by enabling the storage of message payloads in the EDI tables of the tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="cc70f-119">Estos conjuntos de transacciones pueden verse mediante el comando de detalles de vista en la interfaz de usuario de los informes de estado.</span><span class="sxs-lookup"><span data-stu-id="cc70f-119">You can view the transaction sets by using the view details command in the status reporting UI.</span></span>  
  
 <span data-ttu-id="cc70f-120">También se pueden almacenar mensajes AS2 entrantes o salientes, así como MDN en la base de datos sin repudio.</span><span class="sxs-lookup"><span data-stu-id="cc70f-120">You can also store inbound or outbound AS2 messages or MDNs in the non-repudiation database.</span></span> <span data-ttu-id="cc70f-121">Para ver los conjuntos de transacciones o los mensajes AS2, haga clic con el botón secundario en el mensaje del informe de estado y seleccione el comando adecuado.</span><span class="sxs-lookup"><span data-stu-id="cc70f-121">You can view the transaction sets or AS2 messages by right-clicking the message in the status report and selecting the appropriate command.</span></span>  
  
 <span data-ttu-id="cc70f-122">**Componentes de informes de estado**</span><span class="sxs-lookup"><span data-stu-id="cc70f-122">**Status Report Components**</span></span>  
  
 <span data-ttu-id="cc70f-123">Los componentes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que intervienen en los informes de estado son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="cc70f-123">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components involved in status reporting are the following:</span></span>  
  
-   <span data-ttu-id="cc70f-124">Desensamblador EDI en la canalización de recepción EDI que crea y actualiza las entradas de estado en el almacén de datos correspondientes a un intercambio entrante.</span><span class="sxs-lookup"><span data-stu-id="cc70f-124">The EDI Disassembler in the EDI receive pipeline that creates and updates status entries in the data store for an incoming interchange</span></span>  
  
-   <span data-ttu-id="cc70f-125">Ensamblador EDI en la canalización de envío EDI que crea y actualiza las entradas de estado en el almacén de datos correspondientes a un intercambio saliente.</span><span class="sxs-lookup"><span data-stu-id="cc70f-125">The EDI Assembler in the EDI send pipeline that creates and updates status entries in the data store for an outgoing interchange</span></span>  
  
-   <span data-ttu-id="cc70f-126">Los almacenes de datos que guardan las entradas de los informes de estado.</span><span class="sxs-lookup"><span data-stu-id="cc70f-126">The data stores that store the status report entries.</span></span> <span data-ttu-id="cc70f-127">Se trata de la base de datos de importación principal de BAM para el seguimiento de datos y la tabla de contenido del mensaje EDI de la base de datos de seguimiento de BizTalk (BizTalkDTADb) para conjuntos de transacciones EDI o contenido de mensajes AS2.</span><span class="sxs-lookup"><span data-stu-id="cc70f-127">These are the BAM Primary Import database for tracking data and the EDI Message Content table of the BizTalk tracking database (BizTalkDTADb) for EDI transaction sets and/or AS2 message contents</span></span>  
  
-   <span data-ttu-id="cc70f-128">Informes de estado interfaz de usuario en el **concentrador de grupo** página de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] la consola de administración, que se usa para mostrar datos de informes de estado</span><span class="sxs-lookup"><span data-stu-id="cc70f-128">Status reporting UI on the **Group Hub** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, which is used to display status reporting data</span></span>  
  
-   <span data-ttu-id="cc70f-129">Las opciones de propiedad de acuerdo y de propiedad de acuerdo de reserva de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], que se usan para habilitar y configurar los informes de estado.</span><span class="sxs-lookup"><span data-stu-id="cc70f-129">Agreement property and fallback agreement property options in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, which is used to enable and configure status reporting</span></span>  
  
-   <span data-ttu-id="cc70f-130">Servidor de análisis DTA y SQL que aprovecha la infraestructura de BAM.</span><span class="sxs-lookup"><span data-stu-id="cc70f-130">DTA and SQL Analysis Server that leverage the BAM infrastructure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc70f-131">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cc70f-131">In This Section</span></span>  
  
-   [<span data-ttu-id="cc70f-132">Configuración de EDI y AS2 de informes de estado</span><span class="sxs-lookup"><span data-stu-id="cc70f-132">Configuration of EDI and AS2 Status Reporting</span></span>](../core/configuration-of-edi-and-as2-status-reporting.md)  
  
-   [<span data-ttu-id="cc70f-133">Tipos de informes de estado de AS2 y EDI</span><span class="sxs-lookup"><span data-stu-id="cc70f-133">Types of EDI and AS2 Status Reports</span></span>](../core/types-of-edi-and-as2-status-reports.md)  
  
-   [<span data-ttu-id="cc70f-134">Datos almacenados para informes de estado de AS2 y EDI</span><span class="sxs-lookup"><span data-stu-id="cc70f-134">Data Stored for EDI and AS2 Status Reports</span></span>](../core/data-stored-for-edi-and-as2-status-reports.md)  
  
-   [<span data-ttu-id="cc70f-135">Cómo se almacenan los datos para informes de estado de AS2 y EDI</span><span class="sxs-lookup"><span data-stu-id="cc70f-135">How Data Is Stored for EDI and AS2 Status Reports</span></span>](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)