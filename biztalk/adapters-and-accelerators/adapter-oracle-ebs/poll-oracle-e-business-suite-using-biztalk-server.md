---
title: Sondeo Oracle E-Business Suite con BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a22b99a5-1715-4351-b0e0-6b8dcfacd9eb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9b5d0743d39dfcf6cbab7e1da20a8a3fb1382fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218012"
---
# <a name="poll-oracle-e-business-suite-using-biztalk-server"></a>Sondeo Oracle E-Business Suite con BizTalk Server
Puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes de sondeo de base de datos de Oracle. El adaptador proporciona dos maneras de sondeo de la base de datos de Oracle:  
  
-   **Utilizar las instrucciones SELECT**. Puede especificar una instrucción SELECT simple para sondear la base de datos de Oracle. El adaptador ejecuta la instrucción SELECT a los intervalos especificados y devuelve el resultado a los clientes de adaptador.  
  
-   **Uso de procedimientos almacenados**. Puede especificar un procedimiento almacenado para sondear la base de datos de Oracle. El adaptador ejecuta el procedimiento almacenado a los intervalos especificados y devuelve el resultado a los clientes de adaptador.  
  
 La diferencia clave en los dos enfoques es que los clientes de adaptador de manera especifican una instrucción de sondeo que el adaptador utiliza para sondear la base de datos de Oracle. Mientras que la instrucción de sondeo para el primer enfoque es una instrucción SELECT, la instrucción de sondeo para el enfoque de procedimiento almacenado es un mensaje de solicitud que se ejecuta el procedimiento almacenado. Los clientes de adaptador especificar la instrucción de sondeo, para cualquier enfoque para la **PollingInput** propiedad de enlace. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
 Los temas de esta sección proporcionan instrucciones sobre cómo sondear mediante una instrucción SELECT y un procedimiento almacenado.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Sondeo Oracle E-Business Suite con la instrucción SELECT](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement.md)  
  
-   [Uso de procedimientos almacenados de sondeo Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)