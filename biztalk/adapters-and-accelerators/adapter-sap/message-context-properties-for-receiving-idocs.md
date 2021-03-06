---
title: Propiedades de contexto de mensaje para recibir los IDOC | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDOCs, message context properties for receiving
ms.assetid: fadb2284-2f55-49c2-bae9-95325f1be539
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f99c403648ec2fae7fd9ee93f349f7c1fe69434
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999805"
---
# <a name="message-context-properties-for-receiving-idocs"></a>Propiedades de contexto de mensaje para recibir los IDOC
Para recibir un IDOC mediante Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite las siguientes propiedades de contexto de mensaje.  
  
 **Propiedades de registro de Control de IDOC.**  
  
- **TABNAM** -nombre de la estructura de tabla  
  
- **MANDT** -cliente  
  
- **DOCNUM** -número IDOC  
  
- **DOCREL** -versión SAP para IDOC  
  
- **ESTADO** -estado de IDOC  
  
- **DIRECTO** -dirección  
  
- **OUTMOD** -modo de salida  
  
- **EXPRESARSE** : reemplazo en el procesamiento de entrada  
  
- **PRUEBA** -indicador de prueba  
  
- **IDOCTYP** -nombre del tipo básico  
  
- **CIMTYP** -extensión (definida por el cliente)  
  
- **MESTYP** -tipo de mensaje  
  
- **MESCOD** -código del mensaje  
  
- **MESFCT** -mensaje (función)  
  
- **STD** -marca estándar, EDI  
  
- **STDVRS** -EDI estándar, versión y lanzamiento  
  
- **STDMES** -tipo de mensaje EDI  
  
- **SNDPOR** -puerto de remitente (sistema de SAP, subsistema externo)  
  
- **SNDPRT** -tipo de remitente de asociados  
  
- **SNDPFC** -función de remitente de asociados  
  
- **SNDPRN** -número de remitente de asociados  
  
- **SNDSAD** -dirección de remitente (SADR)  
  
- **SNDLAD** -dirección lógica del remitente  
  
- **RCVPOR** -puerto de recepción  
  
- **RCVPRT** -tipo de asociado del receptor  
  
- **RCVPFC** -función de destinatario de asociados  
  
- **RCVPRN** -número de destinatarios de asociados  
  
- **RCVSAD** -dirección de destinatario (SADR)  
  
- **RCVLAD** -dirección lógica del destinatario  
  
- **CREDAT** : creado en  
  
- **CRETIM** -hora de creación  
  
- **REFINT** -archivo de transmisión (intercambio de EDI)  
  
- **REFGRP** -grupo de mensajes (grupo de mensajes EDI)  
  
- **REFMES** -Message (mensaje EDI)  
  
- **ARCKEY** - Key para el archivo de mensaje externo  
  
- **SERIE** -serialización  
  
- **DOCTYP** -tipo IDOC (Esto solo está disponible en EDI_DC. Debe estar presente en la propiedad de contexto, pero debe promocionar solo para la versión 2 idoc)  
  
  **TID** : representa el TID enviado por el sistema SAP para las llamadas TRFC entrantes.  
  
  **GUID** : representa el GUID que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] utiliza internamente. Esto tiene una asignación unívoca con el TID que se recibió desde el sistema SAP.  
  
## <a name="see-also"></a>Vea también  
 [Los mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)