---
title: Empezar a trabajar con el adaptador de BizTalk para SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c3b6e36-ddfb-4ede-adf5-b9762231224b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61a2ecd7ae8020865dff7b67fbc57388d1f15af6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222740"
---
# <a name="get-started-with-the-biztalk-adapter-for-sql"></a>Empezar a trabajar con el adaptador de BizTalk para SQL

  
 Esta sección proporciona información general sobre el adaptador, los requisitos previos y los temas para los usuarios que están familiarizados con Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Describe las características de [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] y las distintas operaciones que se pueden realizar en la base de datos de SQL Server mediante el adaptador.  
  
 ¿Qué es un adaptador? Un adaptador es un componente de software que le permite enviar y recibir mensajes hacia y desde un sistema de línea de negocio (LOB). El objetivo de diseño principal de un adaptador es facilitar el intercambio de documentos empresariales entre socios comerciales. Dado que cada sistema de negocio puede cumplir protocolos y formatos de documento específico, el adaptador debe usar un mecanismo de entrega que cumple con los estándares más habituales y protocolos para proporcionar una interfaz uniforme a los usuarios.  
  
 Los adaptadores en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] puede dividirse en dos amplias categorías:  
  
-   **Los adaptadores de LOB**. Estos adaptadores proporcionan el modelo de programación orientada a los sistemas LOB de acceso — por ejemplo, los adaptadores de SAP o Siebel.  
  
-   **Adaptadores de datos de**. Estos adaptadores proporcionan el modelo de programación orientada a bases de datos de acceso, por ejemplo, los adaptadores para la base de datos de Oracle o SQL Server.  
  
 Hay cinco adaptadores en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:  
  
-   [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] ([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]).  
  
    > [!NOTE]
    >  El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] también está disponible fuera de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] como un adaptador independiente.  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] ([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]).  
  
-   [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] ([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]).  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] ([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]).  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] ([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]).  
  
    > [!NOTE]
    >  El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no está disponible para plataformas de 64 bits.  
  
 Si no ya sabe cómo desea usar el adaptador de SQL en su empresa, se recomienda que primero debe explorar las características y funcionalidad del adaptador se describe en [comprender el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Comprender el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)  
  
-   [Tutoriales del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)  
  
-   [Preguntas más frecuentes](../../adapters-and-accelerators/adapter-sql/sql-adapter-faqs.md)