---
title: Requisitos de hardware y Software para la implementación | Microsoft Docs
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
ms.openlocfilehash: f61a8b66f455aeffee1b5416ebb5911be61fdbec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984661"
---
# <a name="hardware-and-software-requirements-for-deployment"></a>Requisitos de hardware y Software para la implementación
En la tabla siguiente se enumera las recomendaciones de hardware y software y los requisitos para cada servidor de la arquitectura de implementación establecidas. Para obtener más información acerca de cómo configurar el software necesario, consulte [implementar los servidores](../../adapters-and-accelerators/accelerator-swift/deploying-your-servers.md).  

 Para todos los tipos de servidor, elija el espacio en disco, la velocidad de reloj de procesador y la cantidad de memoria de acceso aleatorio (RAM) en función de los requisitos técnicos actuales y planeados (como se describe en [paso 1: instalar la plataforma Base](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)).  


|                    Servidor                    |                                                                                                                                           Recomendaciones de hardware                                                                                                                                            |                                                                                                                                                   Requisitos de software                                                                                                                                                    |
|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|             Controladores de dominio             |                                                                                                                                             -adaptador de red 1                                                                                                                                             |                                       -Microsoft Windows Server 2012 R2 o 2012<br />-Microsoft [!INCLUDE[btsAD](../../includes/btsad-md.md)] Server<br />-Nombres de dominio (DNS)                                       |
|           Servidores Microsoft SQL Server            | -2 adaptadores de red<br />-Opcional: Para los discos de la red de área de almacenamiento (SAN), elija el espacio en disco necesario para el rendimiento medio, rendimiento pico y rendimiento de horas punta más promedio de tamaño del mensaje. La SAN debe dividirse en tres unidades de disco: datos, los registros de transacciones y quórum. |                                                                        -Microsoft Windows Server 2012 R2 o 2012<br />-   [!INCLUDE[SQLServer2008or2005](../../includes/sqlserver2008or2005-md.md)]                                                                         |
|       Servidores de BizTalk para la mensajería        |                                                                                                                                            -2 adaptadores de red                                                                                                                                             |                                                  -Microsoft Windows Server 2012 R2 o 2012<br />-Servidor BizTalk<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]                                                   |
| Servidores de front-end HTTP de BizTalk (sitio MRSR) |                                                                                                                                            -2 adaptadores de red                                                                                                                                             | -Microsoft Windows Server 2012 R2 o 2012<br />-Internet Information Services (IIS)<br />-Servicio message Queue Server con enrutamiento habilitado<br />-Servidor BizTalk<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] |
|     Servidores de BizTalk para las orquestaciones     |                                                                                                                                             -adaptador de red 1                                                                                                                                             |                                                  -Microsoft Windows Server 2012 R2 o 2012<br />-Servidor BizTalk<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]                                                   |

