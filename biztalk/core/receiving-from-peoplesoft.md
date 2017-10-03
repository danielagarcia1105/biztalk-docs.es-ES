---
title: "Recepción desde PeopleSoft | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9acc71ec-05b8-4490-b3ba-0ce7f27a5a6a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11c5add7e71e56f250b95736d97f0434adf72282
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receiving-from-peoplesoft"></a>Recepción desde PeopleSoft
Microsoft Adapter para PeopleSoft Enterprise es un adaptador de envío. El adaptador admite los envíos de solicitud-respuesta para que pueda enviar una consulta y obtener una respuesta. No obstante, si únicamente desea recibir datos de PeopleSoft, deberá realizar otros dos pasos:  
  
1.  Crear una canalización de recepción personalizada con el componente de canalización de establecer espacio de nombres.  
  
2.  Crear un puerto de recepción accesible desde PeopleSoft, como un puerto que use el adaptador HTTP. Use la canalización de recepción personalizada con el puerto de recepción.  
  
## <a name="the-set-namespace-pipeline-component"></a>Componente de canalización de establecer espacio de nombres  
 Los mensajes recibidos de PeopleSoft no incluyen espacios de nombres. El componente de canalización de establecer espacio de nombres permite agregar un espacio de nombres al mensaje entrante.  
  
 La ubicación predeterminada para el componente de canalización de establecer espacio de nombres es C:\Archivos de programa\Microsoft BizTalk Adapters for Enterprise Applications\Pipeline Component. Debe copiar el componente Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll en el directorio Pipeline Component usado por BizTalk. También debe agregar el componente al cuadro de herramientas de Visual Studio para usarlo en el Diseñador de canalizaciones.  
  
 Para obtener información sobre dónde instalar el componente, vea [implementar componentes de canalización](../core/deploying-pipeline-components.md).  
  
 Para obtener información acerca de cómo agregar el componente en el cuadro de herramientas de Visual Studio, vea [cómo utilizar el cuadro de herramientas](../core/how-to-use-the-toolbox.md).  
  
## <a name="configuring-the-set-namespace-pipeline-component"></a>Configuración del componente de canalización de establecer espacio de nombres  
 El componente de canalización de establecer espacio de nombres tiene dos propiedades que se pueden establecer:  
  
|Use|Para|  
|--------------|----------------|  
|**Namespace de destino predeterminado**|Coloque un espacio de nombres fijo en el mensaje entrante.|  
|**Target Namespace XPath**|Extraiga el espacio de nombres del mensaje entrante tomándolo de la ubicación especificada por XPath. Si el componente no encuentra un espacio de nombres válido, registra una advertencia en el registro de eventos de la aplicación y, si está especificado, usa el espacio de nombres de destino predeterminado.|  
  
 Si deja ambas propiedades en blanco, el componente no asigna espacios de nombres a los mensajes entrantes pero escribe advertencias en el registro de eventos de la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de aplicaciones](../core/developing-applications4.md)