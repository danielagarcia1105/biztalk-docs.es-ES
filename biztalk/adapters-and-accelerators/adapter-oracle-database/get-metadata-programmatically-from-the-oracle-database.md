---
title: Obtener metadatos mediante programación de la base de datos de Oracle | Microsoft Docs
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
ms.openlocfilehash: 2380e58605cf401e7ed1138b078d19d5279144f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972877"
---
# <a name="get-metadata-programmatically-from-the-oracle-database"></a>Obtener metadatos mediante programación de la base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es un enlace personalizado de WCF que expone una base de datos de Oracle como un servicio WCF. El adaptador expone la base de datos de Oracle como un servicio autodescriptivo; es decir, un servicio que es capaz de publicación de metadatos acerca de las operaciones que admite. Los metadatos describen la interfaz lógica a un servicio WCF; es decir, el contrato de servicio, mensajes y esquemas de mensaje que se deben usar para interactuar con el servicio.  
  
 Estos metadatos se usan por herramientas tales como:  
  
- El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar representaciones de código administrado del contrato de servicio, y  
  
- El [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar esquemas de mensaje.  
  
  Sin embargo, también puede recuperar metadatos mediante programación desde el adaptador. Por ejemplo, es posible que desee hacer esto para crear una herramienta de recuperación de metadatos personalizados para usar en una aplicación existente.  
  
  El adaptador publica los metadatos a través de dos puntos de conexión:  
  
- Un punto de conexión de WS-Metadata Exchange (MEX). WCF proporciona automáticamente un punto de conexión MEX para todos los enlaces de WCF. Puede usar el intercambio de metadatos para recuperar metadatos para operaciones admitidas por el adaptador en la base de datos de Oracle subyacente.  
  
- Un **IMetadataRetrievalContract** punto de conexión. El **IMetadataRetrievalContract** interfaz se implementa mediante el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]. Clasifica los artefactos de la base de datos de Oracle en varios niveles lógicos y las presenta como un árbol de nodos de metadatos. Puede usar los métodos expuestos por el **IMetadataRetrievalContract** interfaz para examinar y buscar los nodos de este árbol y devolver metadatos para operaciones en el que está interesado.  
  
  Los temas de esta sección describen cómo usar MEX y **IMetadataRetrievalContract** puntos de conexión para recuperar metadatos mediante programación desde el adaptador.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Obtener metadatos mediante WS-Metadata Exchange en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-using-ws-metadata-exchange-in-oracle-database.md)  
  
-   [Obtener metadatos de base de datos de Oracle mediante IMetadataRetrievalContract](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-in-oracle-database-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)