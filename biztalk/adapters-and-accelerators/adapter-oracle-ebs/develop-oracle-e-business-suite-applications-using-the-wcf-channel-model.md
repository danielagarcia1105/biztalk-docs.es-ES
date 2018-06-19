---
title: Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75bb6de1-e11a-4377-af13-e1cb954aaf3f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e99dfa0c69500b86fe086ce0daa81e3ffb62857d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214804"
---
# <a name="develop-oracle-e-business-suite-applications-using-the-wcf-channel-model"></a>Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF
Puede usar el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo del canal para consumir el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] mediante el envío de mensajes XML directamente a través de una instancia del canal creado con el enlace de Oracle EBS.  
  
 Una ventaja de usar el modelo de canal WCF con respecto a las clases fuertemente tipadas y los métodos que se la expone de modelo de servicio WCF es que el modelo del canal proporciona un control más minucioso sobre las operaciones que se realizan en Oracle E-Business Suite. Este control procede del hecho de que en el modelo de canal WCF, puede controlar directamente el contenido de los mensajes que envía a través del canal.  
  
 En determinados escenarios, este nivel adicional de control puede ser beneficioso. Por ejemplo, cuando se usa el modelo de canal WCF para realizar una operación de actualización en una tabla, puede actualizar selectivamente las columnas de las filas de destino mediante la omisión de las columnas de la plantilla de actualización que se pasa en el mensaje. Las únicas columnas que son necesarias son los que tienen "nillable = false" en el archivo WSDL. El método de actualización expuesto por un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente utiliza un parámetro de registro fuertemente tipada de la plantilla que incluye todas las columnas en el esquema de tabla.  
  
 Los temas de esta sección explican cómo realizar operaciones en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] mediante el modelo de canal WCF.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general sobre el modelo de canal WCF con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)  
  
-   [Crear un canal con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-channel-using-oracle-e-business-suite.md)
  
-   [Ejecutar una operación de inserción en una tabla de interfaz en Oracle E-Business Suite mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-oracle-ebs/insert-on-an-interface-table-in-oracle-ebs-using-the-wcf-channel-model.md)  
  
-   [Sondeo Oracle E-Business Suite con la instrucción SELECT con el modelo de canal WCF](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model.md)
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)