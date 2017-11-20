---
title: "Paso 9: Configurar el puerto de envío EDI carga | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71a8a4a7-7c3e-4e33-a9c0-a6445a3cc236
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9de1dff24af11cd03cda2550dcab921aec25d585
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-9-configure-the-edi-payload-send-port"></a><span data-ttu-id="e52c5-102">Paso 9: Configurar el puerto de envío de carga de EDI</span><span class="sxs-lookup"><span data-stu-id="e52c5-102">Step 9: Configure the EDI Payload Send Port</span></span>
<span data-ttu-id="e52c5-103">![Paso 9 de 11](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")</span><span class="sxs-lookup"><span data-stu-id="e52c5-103">![Step 9 of 11](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")</span></span>  
  
 <span data-ttu-id="e52c5-104">En este paso, configurar un puerto de envío para enviar el XML generado a partir de la carga EDI a la aplicación de Contoso back-end, representado por la \\_EDIXMLToContoso carpeta.</span><span class="sxs-lookup"><span data-stu-id="e52c5-104">In this step, you set up a send port to send the XML generated from the EDI payload to the back-end Contoso application, represented by the \\_EDIXMLToContoso folder.</span></span> <span data-ttu-id="e52c5-105">Este puerto de envío utiliza una canalización de envío PassThruTransmit.</span><span class="sxs-lookup"><span data-stu-id="e52c5-105">This send port uses a PassThruTransmit send pipeline.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e52c5-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e52c5-106">Prerequisites</span></span>  
 <span data-ttu-id="e52c5-107">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e52c5-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-sendpayloadedixml-send-port"></a><span data-ttu-id="e52c5-108">Para crear el puerto de envío Send_Payload_EdiXml</span><span class="sxs-lookup"><span data-stu-id="e52c5-108">To create the Send_Payload_EdiXml send port</span></span>  
  
1.  <span data-ttu-id="e52c5-109">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="e52c5-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
2.  <span data-ttu-id="e52c5-110">En el **propiedades de puerto de envío** cuadro de diálogo nombre al puerto de envío **Send_Payload_EdiXml**.</span><span class="sxs-lookup"><span data-stu-id="e52c5-110">In the **Send Port Properties** dialog box, name your send port as **Send_Payload_EdiXml**.</span></span> <span data-ttu-id="e52c5-111">Seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="e52c5-111">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e52c5-112">El tipo de archivo se especifica debido a que la canalización de envío no está llevando a cabo el procesamiento AS2 en el archivo de carga.</span><span class="sxs-lookup"><span data-stu-id="e52c5-112">The FILE type is specified because the send pipeline is not performing AS2 processing on the payload file.</span></span> <span data-ttu-id="e52c5-113">Sólo enruta el archivo de carga a una carpeta local para que pueda ver el conjunto de transacciones EDI.</span><span class="sxs-lookup"><span data-stu-id="e52c5-113">It is just routing the payload file to a local folder so you can see the EDI transaction set.</span></span>  
  
3.  <span data-ttu-id="e52c5-114">En el **propiedades de transporte de archivo** cuadro de diálogo para **carpeta de destino**, busque y seleccione [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_EDIXMLToContoso.</span><span class="sxs-lookup"><span data-stu-id="e52c5-114">In the **FILE Transport Properties** dialog box, for **Destination folder**, browse to and select [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_EDIXMLToContoso.</span></span> <span data-ttu-id="e52c5-115">Deje **nombre de archivo** como **%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="e52c5-115">Leave **File name** as **%MessageID%.xml**.</span></span> <span data-ttu-id="e52c5-116">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e52c5-116">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="e52c5-117">Acepte el valor predeterminado de **PassThruTransmit** para **canalización de envío**.</span><span class="sxs-lookup"><span data-stu-id="e52c5-117">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e52c5-118">Puesto que se usa la canalización de envío PassThruTransmit, la canalización no llevará a cabo ningún procesamiento EDI en el mensaje de carga, pero se enviará a la carpeta local con formato XML producido por la canalización de recepción AS2EdiReceive.</span><span class="sxs-lookup"><span data-stu-id="e52c5-118">Because the PassThruTransmit send pipeline is used, the pipeline will not perform any EDI processing on the payload message, but will be sent to the local folder in the XML format produced by the AS2EdiReceive receive pipeline.</span></span>  
  
5.  <span data-ttu-id="e52c5-119">Haga clic en **filtros** en el árbol de consola.</span><span class="sxs-lookup"><span data-stu-id="e52c5-119">Click **Filters** in the console tree.</span></span> <span data-ttu-id="e52c5-120">Para **propiedad**, escriba **BTS. MessageType**.</span><span class="sxs-lookup"><span data-stu-id="e52c5-120">For **Property**, enter **BTS.MessageType**.</span></span> <span data-ttu-id="e52c5-121">Para **operador**, escriba  **==** .</span><span class="sxs-lookup"><span data-stu-id="e52c5-121">For **Operator**, enter **==**.</span></span> <span data-ttu-id="e52c5-122">Para **valor**, escriba `http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`.</span><span class="sxs-lookup"><span data-stu-id="e52c5-122">For **Value**, enter `http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e52c5-123">Este filtro garantiza que el puerto de envío sólo recogerá los mensajes de carga X12 864 del cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e52c5-123">This filter ensures that this send port will only pick up X12 864 payload messages from the MessageBox.</span></span>  
  
6.  <span data-ttu-id="e52c5-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e52c5-124">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="e52c5-125">En el **puertos de envío** panel de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **Send_Payload_EdiXml** puerto de envío y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="e52c5-125">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send_Payload_EdiXml** send port, and then click **Start**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e52c5-126">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e52c5-126">Next Steps</span></span>  
 <span data-ttu-id="e52c5-127">Crear un AS2 y X12 los partners de acuerdo entre los dos comerciales, como se describe en [paso 10: configurar la X12 y AS2 acuerdo de socios comerciales](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)</span><span class="sxs-lookup"><span data-stu-id="e52c5-127">You create an AS2 and X12 agreement between the two trading partners, as described in [Step 10: Configure the X12 and AS2 Trading Partner Agreement](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e52c5-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="e52c5-128">See Also</span></span>  
 [<span data-ttu-id="e52c5-129">Tutorial 3: Tutorial de AS2</span><span class="sxs-lookup"><span data-stu-id="e52c5-129">Tutorial 3: AS2 Tutorial</span></span>](../core/tutorial-3-as2-tutorial.md)