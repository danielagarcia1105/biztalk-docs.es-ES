---
title: Obtener metadatos mediante programación de la base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving programmatically from the Oracle database
ms.assetid: 28a55935-6078-41d0-abfa-ac86e9ca8471
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c36fcd6a791f1d960a4dd4dfd78ca199d2e49cb5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-programmatically-from-the-oracle-database"></a>Obtener metadatos mediante programación de la base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es un enlace personalizado de WCF que expone una base de datos de Oracle como un servicio WCF. El adaptador expone la base de datos de Oracle como un servicio autodescriptivo; es decir, un servicio que es capaz de publicación de metadatos acerca de las operaciones que admite. Los metadatos describen la interfaz lógica a un servicio WCF; es decir, el contrato de servicio, mensajes y los esquemas de mensaje que se deben usar para interactuar con el servicio.  
  
 Estos metadatos se utilizan con herramientas como:  
  
-   El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar representaciones de código administrado del contrato de servicio, y  
  
-   El [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar esquemas de mensaje.  
  
 Sin embargo, también puede recuperar metadatos mediante programación desde el adaptador. Por ejemplo, puede realizar esta operación para crear una herramienta de recuperación de metadatos personalizados para utilizar en una aplicación existente.  
  
 El adaptador publica los metadatos a través de dos puntos de conexión:  
  
-   Un extremo de WS-Metadata Exchange (MEX). WCF proporciona automáticamente un extremo MEX para todos los enlaces de WCF. Puede usar el intercambio de metadatos para recuperar metadatos para operaciones admitidas por el adaptador en la base de datos de Oracle subyacente.  
  
-   Un **IMetadataRetrievalContract** punto de conexión. El **IMetadataRetrievalContract** interfaz se implementa mediante el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]. Clasifica los artefactos de la base de datos de Oracle en varios niveles lógicos y los presenta como un árbol de nodos de metadatos. Puede usar los métodos expuestos por el **IMetadataRetrievalContract** interfaz para examinar y buscar los nodos de este árbol y para devolver los metadatos para las operaciones en el que esté interesado.  
  
 Los temas de esta sección describen cómo utilizar MEX y **IMetadataRetrievalContract** puntos de conexión para recuperar metadatos mediante programación desde el adaptador.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Obtener metadatos con WS-Metadata Exchange en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-using-ws-metadata-exchange-in-oracle-database.md)  
  
-   [Obtener metadatos de base de datos de Oracle mediante IMetadataRetrievalContract](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-in-oracle-database-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)