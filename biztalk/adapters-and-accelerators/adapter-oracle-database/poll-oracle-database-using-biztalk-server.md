---
title: Sondeo de base de datos de Oracle mediante BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c3aef30-956d-4585-b2de-7eebb919fab5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2578d00518a9f1632e690e84db04426575619109
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214180"
---
# <a name="poll-oracle-database-using-biztalk-server"></a>Sondeo de base de datos de Oracle mediante BizTalk Server
Puede configurar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para recibir mensajes de sondeo de base de datos de Oracle. El adaptador proporciona dos maneras de sondeo de la base de datos de Oracle:  
  
-   **Utilizar las instrucciones SELECT**. Puede especificar una instrucción SELECT simple para sondear las tablas y vistas en la base de datos de Oracle. El adaptador ejecuta la instrucción SELECT a los intervalos especificados y devuelve el resultado a los clientes de adaptador.  
  
-   **Usar procedimientos almacenados, funciones o procedimientos o funciones dentro de un paquete**. Puede especificar un procedimiento almacenado, función o procedimiento o función dentro de un paquete para sondear la base de datos de Oracle. El adaptador ejecuta el mensaje de solicitud a los intervalos especificados y devuelve el resultado a los clientes de adaptador.  
  
 La diferencia clave en los dos enfoques es que los clientes de adaptador de manera especifican una instrucción de sondeo que el adaptador utiliza para sondear la base de datos de Oracle. Mientras que la instrucción de sondeo para el primer enfoque es una instrucción SELECT, la instrucción de sondeo para otro enfoque es un mensaje de solicitud que se ejecuta el procedimiento almacenado, función o procedimiento o función dentro de un paquete. Los clientes de adaptador especificar la instrucción de sondeo, para cualquier enfoque, en la **PollingStatement** propiedad de enlace. Para obtener más información acerca de las propiedades de enlace, vea [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).  
  
 Los temas de esta sección proporcionan instrucciones sobre cómo sondear mediante una instrucción SELECT y un procedimiento almacenado, función o procedimiento o función dentro de un paquete.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Sondeo de base de datos de Oracle mediante la instrucción SELECT](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-the-select-statement.md)  
  
-   [Sondeo de base de datos de Oracle mediante procedimientos almacenados, funciones, o empaquetados procedimientos y funciones](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-db-using-stored-procedures-functions-or-packaged-procedures.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)