---
title: El modelo de servicio mediante WCF sondeo Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96670a39-4fec-49bf-85d1-947b1a1bc750
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2f8c9f16ed93e2866da0cbd55021edfdb2bd863
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995349"
---
# <a name="poll-oracle-e-business-suite-using-the-wcf-service-model"></a>Sondear Oracle E-Business Suite mediante el modelo de servicio WCF
Puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes basados en sondeos de la base de datos de Oracle. El adaptador proporciona dos maneras de sondear la base de datos de Oracle:  
  
- **Utilizar las instrucciones SELECT**. Puede especificar una instrucción SELECT simple para sondear la base de datos de Oracle. El adaptador ejecuta la instrucción SELECT a intervalos especificados y devuelve el resultado a los clientes del adaptador.  
  
- **Uso de procedimientos almacenados**. Puede especificar un procedimiento almacenado para sondear la base de datos de Oracle. El adaptador ejecuta el procedimiento almacenado a intervalos especificados y devuelve el resultado a los clientes del adaptador.  
  
  La diferencia clave en los dos enfoques es que los clientes del adaptador de manera especifican una instrucción de sondeo que utiliza el adaptador para sondear la base de datos de Oracle. Aunque la instrucción de sondeo para el primer enfoque es una instrucción SELECT simple, la instrucción de sondeo para el enfoque de procedimiento almacenado es un mensaje de solicitud que se ejecuta el procedimiento almacenado. Los clientes del adaptador especifican la instrucción de sondeo para cualquier enfoque, para el **PollingInput** enlaza la propiedad. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
  Los temas de esta sección proporcionan instrucciones sobre cómo sondear con una instrucción SELECT y un procedimiento almacenado.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Sondear Oracle E-Business Suite mediante la instrucción SELECT con el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-service-model.md)  
  
-   [Sondear Oracle E-Business Suite mediante procedimientos almacenados con el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures-with-the-wcf-service-model.md)  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)