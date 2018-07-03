---
title: Administrar el control de versiones de adaptador con el SDK de adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb596fdd-251c-4978-9f33-cf2883d281d8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dfb323bf810f69c8a8f1f857b0d0240c14c4d18
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975189"
---
# <a name="manage-adapter-versioning-with-the-wcf-lob-adapter-sdk"></a>Administrar el control de versiones de adaptador con el SDK de adaptador LOB de WCF
Después de la implementación inicial de los adaptadores y potencialmente varias horas durante su duración, adaptadores (y los puntos de conexión que exponen) es posible que deba cambiarse por una serie de motivos. Estas razones incluyen el cambio de las necesidades empresariales, los requisitos de tecnología de información o problemas con la línea de negocio sistema de o del propio adaptador. Este tema describen varias estrategias para controlar el control de versiones para los adaptadores que se escriben con el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].  
  
## <a name="versioning-and-windows-communication-foundation"></a>Control de versiones y Windows Communication Foundation  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] se basa en [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] y se basa en su infraestructura para intercambiar mensajes entre sistemas. Mediante los mecanismos que [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] expone, versiones se pueden controlar los contratos de datos y servicios. Para obtener más información, incluidos los procedimientos recomendados para las versiones de servicio, consulte [versiones del servicio](http://go.microsoft.com/fwlink/?LinkId=85497) en el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] referencia en línea. Para obtener más información, incluidos los procedimientos recomendados para las versiones de contratos de datos, vea [versiones de contratos de datos](http://go.microsoft.com/fwlink/?LinkId=120177) en el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] referencia en línea.  
  
## <a name="versioning-scenarios"></a>Escenarios de control de versiones  
 Hay dos escenarios de control de versiones principales:  
  
- Una versión de adaptador es compatible con varias versiones del sistema de destino.  
  
- Dos o más versiones de adaptador compatible con el mismo sistema o dos o más sistemas diferentes.  
  
  También es podrán que deba liberar una nueva versión del adaptador de si actualiza a la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] afectan a la funcionalidad existente.  
  
  Cada uno de estos escenarios requiere una estrategia de control de versiones diferentes.  
  
> [!NOTE]
>  El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no aplica los escenarios de control de versiones específico. Se deja al programador para determinar los requisitos de control de versiones para un adaptador.  
  
### <a name="one-adapter-supports-multiple-versions-of-target-system"></a>Un adaptador es compatible con varias versiones del sistema de destino  
 Cuando el adaptador es compatible con varias versiones del sistema de destino, debe exponer una o varias propiedades de enlace que pueden usarse para identificar la versión deseada. Por ejemplo, un adaptador puede admitir varias bibliotecas de comunicación proporcionadas por el proveedor del sistema de destino. Con una propiedad de enlace personalizado denominada "LibraryVersion", el consumidor de adaptador podría elegir qué biblioteca usar según el entorno de implementación u otros requisitos.  
  
### <a name="two-or-more-adapters-support-one-version-of-target-system"></a>Dos o más adaptadores admiten una versión de sistema de destino  
 En este caso, cada adaptador debe usar un esquema único (ContosoV1: / / y ContosoV2: / /) y un nombre único del enlace (ContosoV1Binding y ContosoV2Binding). Los proveedores deben considerar el uso de su nombre en el esquema y el nombre del enlace así (por ejemplo, Microsoft.ContosoV1:// y Microsoft.ContosoV1Binding).  
  
### <a name="new-versions-of-the-wcf-lob-adapter-sdk"></a>Nuevas versiones de SDK de adaptador LOB de WCF  
 Cuando las nuevas versiones de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] son publicado, podrá instalar la nueva versión sin tener que recompilar el adaptador, ya que [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] versiones ser compatible con versiones anteriores. Sin embargo, debe evaluar las nuevas versiones para determinar si hay un cambio en la funcionalidad que depende de su adaptador, o si hay nueva funcionalidad que el adaptador se beneficiaría de la implementación.  
  
## <a name="see-also"></a>Vea también  
 [Prácticas recomendadas de desarrollo mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)