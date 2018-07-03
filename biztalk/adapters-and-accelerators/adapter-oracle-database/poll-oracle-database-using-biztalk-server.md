---
title: Sondeo de base de datos de Oracle con BizTalk Server | Microsoft Docs
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
ms.openlocfilehash: d819abc957eb46dc430befb01cbcae0b8b55ca48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996101"
---
# <a name="poll-oracle-database-using-biztalk-server"></a>Sondeo de base de datos de Oracle con BizTalk Server
Puede configurar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para recibir mensajes basados en sondeos de base de datos de Oracle. El adaptador proporciona dos maneras de sondear la base de datos de Oracle:  
  
- **Utilizar las instrucciones SELECT**. Puede especificar una instrucción SELECT simple para sondear las tablas y vistas de la base de datos de Oracle. El adaptador ejecuta la instrucción SELECT a intervalos especificados y devuelve el resultado a los clientes del adaptador.  
  
- **Mediante procedimientos almacenados, funciones, procedimientos o funciones dentro de un paquete**. Puede especificar un procedimiento almacenado, función o procedimiento o función dentro de un paquete para sondear la base de datos de Oracle. El adaptador el mensaje de solicitud ejecuta a intervalos especificados y devuelve el resultado a los clientes del adaptador.  
  
  La diferencia clave en los dos enfoques es que los clientes del adaptador de manera especifican una instrucción de sondeo que utiliza el adaptador para sondear la base de datos de Oracle. Aunque la instrucción de sondeo para el primer enfoque es una instrucción SELECT simple, la instrucción de sondeo para el otro enfoque es un mensaje de solicitud que se ejecuta el procedimiento almacenado, función o procedimiento o función dentro de un paquete. Los clientes del adaptador especifican la instrucción de sondeo para cualquier enfoque, en el **PollingStatement** enlaza la propiedad. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).  
  
  Los temas de esta sección proporcionan instrucciones sobre cómo sondear con una instrucción SELECT y un procedimiento almacenado, función o procedimiento o función dentro de un paquete.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Sondeo de base de datos de Oracle mediante la instrucción SELECT](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-the-select-statement.md)  
  
-   [Sondeo de base de datos de Oracle mediante procedimientos almacenados, funciones, o empaquetados procedimientos y funciones](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-db-using-stored-procedures-functions-or-packaged-procedures.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)