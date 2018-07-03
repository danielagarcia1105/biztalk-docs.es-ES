---
title: Modelo de proceso de confirmación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, process flow
- ACK process model
ms.assetid: 3c6a5eef-57ef-41f7-9782-e1cbc4dd78e1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98fac157c3c3bfa62825fd3c5cb59c68aac528e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970637"
---
# <a name="ack-process-model"></a><span data-ttu-id="dc85e-102">Modelo de proceso de confirmación</span><span class="sxs-lookup"><span data-stu-id="dc85e-102">ACK Process Model</span></span>
<span data-ttu-id="dc85e-103">La siguiente secuencia de pasos describe el modelo de proceso de confirmación (ACK):</span><span class="sxs-lookup"><span data-stu-id="dc85e-103">The following sequence of steps describes the acknowledgment (ACK) process model:</span></span>  
  
1. <span data-ttu-id="dc85e-104">Cuando el personal de admisión registrar información de admisión de pacientes en el sistema de pacientes (ADT), el sistema genera un evento de desencadenador.</span><span class="sxs-lookup"><span data-stu-id="dc85e-104">When the admissions personnel log patient admission information into the Admissions System (ADT), the system generates a trigger event.</span></span>  
  
2. <span data-ttu-id="dc85e-105">El sistema ADT genera un mensaje de registro de paciente de HL7 codificado (ADT ^ A04) y lo entrega al Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="dc85e-105">The ADT system generates an HL7-encoded Patient Registration message (ADT^A04) and delivers it to BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).</span></span>  
  
3. <span data-ttu-id="dc85e-106">El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sistema aplica un contenedor MLLP en el ADT ^ A04 mensaje y lo envía a la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor de interfaz.</span><span class="sxs-lookup"><span data-stu-id="dc85e-106">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] system applies an MLLP wrapper on the ADT^A04 message and routes it to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
   -   <span data-ttu-id="dc85e-107">Requisito de confirmación 'Modo Original' está preconfigurado</span><span class="sxs-lookup"><span data-stu-id="dc85e-107">Requirement of 'Original Mode' Acknowledgment is preconfigured</span></span>  
  
   -   <span data-ttu-id="dc85e-108">MSH 15 y 16 tienen valores null</span><span class="sxs-lookup"><span data-stu-id="dc85e-108">MSH 15 and 16 have null values</span></span>  
  
4. <span data-ttu-id="dc85e-109">El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] interfaz motor valida el mensaje y si se produce la validación correctamente, genera el mensaje de confirmación con el estado **MSA01 = AA**.</span><span class="sxs-lookup"><span data-stu-id="dc85e-109">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine validates the message and if successful validation occurs, it generates the ACK message with the status **MSA01 = AA**.</span></span>  
  
5. <span data-ttu-id="dc85e-110">El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor interfaz transforma el ADT ^ A04 mensaje delimitarlo con contenedores MLLP y enrutarlo a del sistema de información de laboratorio (LIS).</span><span class="sxs-lookup"><span data-stu-id="dc85e-110">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine transforms the ADT^A04 message by enclosing it with MLLP wrappers and routing it to the Lab Information System (LIS).</span></span>  
  
   - [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="dc85e-111"> preconfigura la confirmación 'Modo mejorado'</span><span class="sxs-lookup"><span data-stu-id="dc85e-111"> preconfigures 'Enhanced Mode' Acknowledgment</span></span>  
  
   - <span data-ttu-id="dc85e-112">MSH 15 y 16 = AL</span><span class="sxs-lookup"><span data-stu-id="dc85e-112">MSH 15 and 16 = AL</span></span>  
  
6. <span data-ttu-id="dc85e-113">La capa de interfaz de LIS valida el encabezado al confirmar el mensaje y generar una confirmación Aceptar con el estado **MSA1 = CA**.</span><span class="sxs-lookup"><span data-stu-id="dc85e-113">The LIS Interface Layer validates the header by committing the message and generating an ACCEPT ACK with the status **MSA1 = CA**.</span></span> <span data-ttu-id="dc85e-114">La capa de interfaz enruta el mensaje con el contenedor MLLP el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor de interfaz.</span><span class="sxs-lookup"><span data-stu-id="dc85e-114">The interface layer routes the message with the MLLP wrapper to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
7. <span data-ttu-id="dc85e-115">La capa de interfaz de LIS valida el mensaje completo y genera una confirmación de la aplicación con el estado **MSA1 = AA**.</span><span class="sxs-lookup"><span data-stu-id="dc85e-115">The LIS Interface Layer validates the entire message and generates an APPLICATION ACK with the status **MSA1 = AA**.</span></span> <span data-ttu-id="dc85e-116">La capa de interfaz enruta el mensaje con el contenedor MLLP el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor de interfaz.</span><span class="sxs-lookup"><span data-stu-id="dc85e-116">The interface layer routes the message with the MLLP wrapper to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
   - [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="dc85e-117"> preconfigura 'Confirmación necesaria' reconocer la confirmación</span><span class="sxs-lookup"><span data-stu-id="dc85e-117"> preconfigures 'ACK Required' acknowledging the acknowledgment</span></span>  
  
   - <span data-ttu-id="dc85e-118">15 de MSH = AL., lo que indica que el sistema receptor debe confirmar la confirmación con un mensaje de confirmación de aceptación</span><span class="sxs-lookup"><span data-stu-id="dc85e-118">MSH 15 = AL, which indicates that the receiving system must acknowledge the ACK with a Commit Accept Message</span></span>  
  
8. <span data-ttu-id="dc85e-119">La capa de interfaz de LIS entrega el mensaje a la capa de aplicación según los requisitos de formato.</span><span class="sxs-lookup"><span data-stu-id="dc85e-119">The LIS Interface layer delivers the message to the Application Layer in accordance with the format requirement.</span></span>  
  
9. <span data-ttu-id="dc85e-120">El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] interfaz motor valida la confirmación recibida de la capa de interfaz de LIS (en el paso 7 anterior) y responde con una confirmación a la capa de interfaz de LIS con el estado **MSA1 = CA**.</span><span class="sxs-lookup"><span data-stu-id="dc85e-120">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine validates the ACK received from the LIS Interface Layer (in step 7 above) and responds with an ACK back to the LIS Interface Layer with the status **MSA1= CA**.</span></span>  
  
10. <span data-ttu-id="dc85e-121">Un usuario del sistema LIS revisa la información del paciente.</span><span class="sxs-lookup"><span data-stu-id="dc85e-121">A user of the LIS System reviews the Patient information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc85e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc85e-122">See Also</span></span>  
 <span data-ttu-id="dc85e-123">[Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="dc85e-123">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 [<span data-ttu-id="dc85e-124">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="dc85e-124">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)