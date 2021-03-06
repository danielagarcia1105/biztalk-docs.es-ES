---
title: WCF y metadatos de servicio modelo con Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, metadata
- metadata, and the WCF service model
ms.assetid: 3aca1835-fb9e-4841-a920-078da0b3fe76
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb47a69efc6522eb6868ce2ecda5c608d2652c99
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752788"
---
# <a name="metadata-and-the-wcf-service-model-with-siebel"></a>Los metadatos y el modelo de servicio WCF con Siebel
En el modelo de servicio WCF, se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutile.exe) para generar una clase de proxy, la clase de cliente WCF: a través de que el código puede invocar operaciones en el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].  
  
 Estas herramientas usan los metadatos expuestos por el adaptador para generar:  
  
- Una interfaz .NET anotada que representa el contrato de servicio para las operaciones de destino. Esta interfaz se denomina el contrato de servicio WCF.  
  
- Anotado clases que representan el apoyo de los contratos de mensaje, contratos de operación y contratos de datos para el contrato de servicio.  
  
- Una clase de cliente WCF cuyos métodos pueden usarse para invocar los métodos de servicio (operaciones) expuestos por el contrato de servicio WCF.  
  
  Para obtener ayuda acerca de la estructura de este genera código, vea "Descripción genera código de cliente" en [ http://go.microsoft.com/fwlink/?LinkId=98365 ](http://go.microsoft.com/fwlink/?LinkId=98365). Este tema describe específicamente a código que genera svcutil.exe, pero su contenido también es aplicable al código que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.  
  
  Para obtener información acerca de cómo generar una clase de cliente WCF para las operaciones de destino y las diferencias entre svcutil.exe y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de solución de Siebel](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Siebel mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)
