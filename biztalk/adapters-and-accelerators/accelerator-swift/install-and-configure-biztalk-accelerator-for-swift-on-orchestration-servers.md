---
title: Instalar y configurar el Acelerador de BizTalk para SWIFT en los servidores de orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on orchestration server
ms.assetid: 127113ae-46b4-4290-a2c1-6a3db04cd178
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6811d3dd79de75968b3976b7568075158017609d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985086"
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-orchestration-servers"></a>Instalar y configurar el Acelerador de BizTalk para SWIFT en los servidores de orquestación
Esta sección describe cómo instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] en los servidores de orquestación. Estos servidores se utilizan principalmente para ejecutar la orquestación de conciliación y reparación de FIN y la orquestación de envío de reparación/nuevo mensaje.  

### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-orchestration-server"></a>Para instalar y configurar el Acelerador de BizTalk para SWIFT en el servidor de orquestación  

1. Realizar una instalación personalizada de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]. Instalar el **MRSR** característica.  

   > [!NOTE]
   >  No es necesario instalar los componentes Web para la característica de reparación de mensajes y nuevo envío porque este servidor no tiene el sitio MRSR.  

   > [!NOTE]
   >  Una vez completada la instalación, se inicia el Asistente para configuración.  

2. En Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] configuración de la consola, configure **MCRR**.
