---
title: Sondear Oracle E-Business Suite con BizTalk Server | Microsoft Docs
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
ms.openlocfilehash: b8180b3b671c87b5dcd0d41477e20b6d175f1cce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974221"
---
# <a name="poll-oracle-e-business-suite-using-biztalk-server"></a>Sondear Oracle E-Business Suite con BizTalk Server
Puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes basados en sondeos de base de datos de Oracle. El adaptador proporciona dos maneras de sondear la base de datos de Oracle:  
  
- **Utilizar las instrucciones SELECT**. Puede especificar una instrucción SELECT simple para sondear la base de datos de Oracle. El adaptador ejecuta la instrucción SELECT a intervalos especificados y devuelve el resultado a los clientes del adaptador.  
  
- **Uso de procedimientos almacenados**. Puede especificar un procedimiento almacenado para sondear la base de datos de Oracle. El adaptador ejecuta el procedimiento almacenado a intervalos especificados y devuelve el resultado a los clientes del adaptador.  
  
  La diferencia clave en los dos enfoques es que los clientes del adaptador de manera especifican una instrucción de sondeo que utiliza el adaptador para sondear la base de datos de Oracle. Aunque la instrucción de sondeo para el primer enfoque es una instrucción SELECT simple, la instrucción de sondeo para el enfoque de procedimiento almacenado es un mensaje de solicitud que se ejecuta el procedimiento almacenado. Los clientes del adaptador especifican la instrucción de sondeo para cualquier enfoque, para el **PollingInput** enlaza la propiedad. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
  Los temas de esta sección proporcionan instrucciones sobre cómo sondear con una instrucción SELECT y un procedimiento almacenado.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Sondear Oracle E-Business Suite mediante la instrucción SELECT](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement.md)  
  
-   [Sondear Oracle E-Business Suite mediante procedimientos almacenados](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)