---
title: Requisitos de hardware y Software para la implementación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, hardware requirements
- deploying, software requirements
ms.assetid: 1dd9c4bb-b724-4195-8496-eff95cd1548a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e772c409533e5ef6e3fedd13e3db7acbfdc572c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004605"
---
# <a name="hardware-and-software-requirements-for-deployment"></a>Requisitos de hardware y Software para la implementación
En la tabla siguiente se enumera los requisitos para cada servidor de la arquitectura de implementación establecidas y recomendaciones de hardware y software. Para obtener más información acerca de cómo configurar el software necesario, consulte [implementar los servidores](../../adapters-and-accelerators/accelerator-swift/deploying-your-servers.md).  
  
 Para todos los tipos de servidor, elija el espacio de disco duro, la velocidad de reloj de procesador y la cantidad de memoria de acceso aleatorio (RAM) en función de los requisitos técnicos actuales y previstos (como se describe en [paso 1: instalación de la plataforma Base](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)).  
  
|Server|Recomendaciones de hardware|Requisitos de software|  
|------------|------------------------------|---------------------------|  
|Controladores de dominio|-adaptador de red 1|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 o 2012<br />-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsAD](../../includes/btsad-md.md)] Server<br />-Nombres de dominio (DNS)|  
|Servidores de Microsoft SQL|-2 adaptadores de red<br />-Opcional: Para los discos de la red de área de almacenamiento (SAN), elija el espacio de disco duro necesario para el rendimiento medio, el rendimiento de pico y el rendimiento de horas punta más promedio de tamaño del mensaje. La SAN debe dividirse en tres unidades de disco: quórum, datos y registros de transacciones.|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 o 2012<br />-   [!INCLUDE[SQLServer2008or2005](../../includes/sqlserver2008or2005-md.md)]|  
|Servidores de BizTalk para la mensajería de|-2 adaptadores de red|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 o 2012<br />-Servidor BizTalk<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]|  
|Servidores front-end de HTTP de BizTalk (sitio MRSR)|-2 adaptadores de red|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 o 2012<br />-Internet Information Services (IIS)<br />-Servicio message Queue Server con enrutamiento habilitado<br />-Servidor BizTalk<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]|  
|Servidores de BizTalk de orquestaciones|-adaptador de red 1|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 o 2012<br />-Servidor BizTalk<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]|