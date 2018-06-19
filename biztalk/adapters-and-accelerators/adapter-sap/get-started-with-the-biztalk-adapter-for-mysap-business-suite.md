---
title: Empezar a trabajar con el adaptador de BizTalk para mySAP Business Suite | Documentos de Microsoft
description: Instalar RFC personalizadas, obtenga información acerca del adaptador, completar tareas RFC e IDOC en SAP, paso a través de tutoriales para usar el adaptador de mySAP en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2013253-f911-4e35-a33a-b4a9bcb136aa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e5607a255f50bf5295d4ea22c9a680d86f38e5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216324"
---
# <a name="get-started-with-the-biztalk-adapter-for-mysap-business-suite"></a>Empezar a trabajar con el adaptador de BizTalk para mySAP Business Suite
Esta sección proporciona información general sobre el adaptador, los requisitos previos y los temas para los usuarios que están familiarizados con Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Describe las características de [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] y las distintas operaciones que se pueden realizar en el sistema SAP mediante el adaptador.  

## <a name="what-is-an-adapter"></a>¿Qué es un adaptador? 
Un adaptador es un componente de software que le permite enviar y recibir mensajes hacia y desde un sistema de línea de negocio (LOB). El objetivo de diseño principal de adaptadores es facilitar el intercambio de documentos empresariales entre socios comerciales. Dado que cada sistema de negocio puede cumplir protocolos y formatos de documento específico, el adaptador debe usar un mecanismo de entrega que cumple con los estándares más habituales y protocolos para proporcionar una interfaz uniforme a los usuarios.  
  
 Los adaptadores se pueden dividir en dos amplias categorías:  
  
-   **Los adaptadores de LOB**. Estos adaptadores proporcionan el modelo de programación orientada a los sistemas LOB de acceso — por ejemplo, los adaptadores de SAP o Siebel.  
  
-   **Adaptadores de datos de**. Estos adaptadores proporcionan el modelo de programación orientada a bases de datos de acceso, por ejemplo, un adaptador para la base de datos de Oracle o SQL Server.  
  
 Hay cinco adaptadores en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:  
  
-   [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)](el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)](el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])  
  
-   [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)](el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)](el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), incluido [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)](el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), incluido [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])  
  
    > [!NOTE]
    >  El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no está disponible para plataformas de 64 bits.  
  
 Si no ya sabe cómo desea usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] en su empresa, se recomienda que primero debe explorar características y funcionalidad del adaptador se describe en [comprender el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md) .  
  
## <a name="next-steps"></a>Pasos siguientes  
- [Instalar RFC personalizadas para el proveedor de datos para SAP](install-custom-rfcs-for-the-data-provider-for-sap.md)
  
-   [Comprender el adaptador de BizTalk para mySAP Business Suite](understand-biztalk-adapter-for-mysap-business-suite.md)  

- [Completar tareas RFC e IDOC en SAP](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)
  
-   [Tutoriales del adaptador SAP](sap-adapter-tutorials.md)  