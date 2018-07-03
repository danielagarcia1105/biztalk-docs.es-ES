---
title: Ejemplos del adaptador de Siebel | Microsoft Docs
description: Ejemplos de adaptador de Siebel WCF que pueden usarse con BizTalk Server, el modelo de servicio WCF y el proveedor de datos para Siebel
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 069d676e-211e-474c-9cf5-c660fdd22014
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 608603ead6b708722a7fc51cd2d5e2849812b408
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014829"
---
# <a name="samples-for-the-siebel-adapter"></a>Ejemplos para el adaptador de Siebel
Ejemplos para [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] se clasifican en categorías:  

- Ejemplos de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  

- Ejemplos de modelo de servicio WCF  

- Ejemplos de [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]  


Los ejemplos están disponibles en [BizTalk Adapter Pack 2010: ejemplos del adaptador de Siebel](https://www.microsoft.com/download/details.aspx?id=6492). 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]

En la lista siguiente describe los ejemplos.

## <a name="biztalk-server-samples"></a>Ejemplos de BizTalk Server  

|      Nombre del directorio de ejemplo      |                                                                                     Descripción                                                                                     |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         BusinessService         |                    Se muestra cómo invocar un servicio de negocio de Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].                     |
|             MVLDemo             |                Muestra cómo trabajar con varios valores (MVLs) de vínculos de Siebel utilizando el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].                 |
|          SiebelAccount          |        Muestra cómo insertar registros en el componente de cuenta empresarial de Siebel utilizando el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].        |
| SiebelAdapterIntegrationObjects | Se muestra cómo invocar un servicio de negocio de Siebel, que funciona con objetos de integración, mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. |
|         SiebelPicklist          |      Muestra cómo insertar valores de tipos de lista desplegable en un componente de negocio de Siebel con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].      |

## <a name="wcf-service-model-samples"></a>Ejemplos de modelo de servicio WCF 

|Nombre del directorio de ejemplo|Descripción|  
|---------------------------|-----------------|  
|AccountInsertDelete|Muestra cómo realizar Insert, Update, Delete y consultar las operaciones en un componente empresarial de Siebel. El ejemplo inserta un registro en el componente de negocio de la cuenta del objeto comercial cuenta, actualiza el registro y, por último, elimina. Antes y después de cada operación se realiza una operación de consulta en el componente empresarial para comprobar los resultados.|  
|Servicios empresariales|Se muestra cómo invocar un método de servicio de negocio de Siebel, marca de tiempo y muestra los resultados en la consola.|  
|MVL|Muestra cómo trabajar con vínculos de varios valores en un componente empresarial de Siebel mediante el uso de las operaciones de consulta asociar, desasociar y secundarios. El ejemplo muestra todos los contactos asociados con una cuenta. También muestra cómo asociar y desasociar un contacto de una cuenta.|  

## <a name="data-provider-for-siebel-sample"></a>Proveedor de datos de ejemplo de Siebel  

| Nombre del directorio de ejemplo |                                                Descripción                                                 |
|-----------------------|------------------------------------------------------------------------------------------------------------|
|      ado de Siebel       | Muestra cómo usar el [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]. |

## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)