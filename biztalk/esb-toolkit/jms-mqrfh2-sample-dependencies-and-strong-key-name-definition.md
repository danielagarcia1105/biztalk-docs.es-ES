---
title: "Dependencias de ejemplo JMS MQRFH2 y clave segura nombrar definición | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3a5cdce-dcdf-48df-91a5-8cf2afce9255
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f3e2f76a972f851322f82f2e89b285db907d799
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="jms-mqrfh2-sample-dependencies-and-strong-key-name-definition"></a>Definición de nombre de clave seguro y dependencias de ejemplo MQRFH2 JMS
El proyecto de Visual Studio ESB. JMS. PipelineComponents depende de la siguiente carpeta:  
  
-   \<Directorio de instalación de BizTalk Server\>. Esta carpeta proporciona acceso a los espacios de nombres siguientes:  
  
    -   **Microsoft::BizTalk::Message::Interop**  
  
    -   **Microsoft::BizTalk::Component::Interop**  
  
## <a name="the-strong-name-key-definition"></a>La definición de clave de nombre seguro  
 Normalmente, la definición de clave de nombre seguro se encuentra en el archivo AssemblyInfo.cpp. Sin embargo, esto podría entrar en conflicto con el archivo de manifiesto de C++ que el compilador agrega al ensamblado después de leer el archivo AssemblyInfo.cpp. Este conflicto impediría que cualquier intento de colocar el archivo en la caché global de ensamblados. En su lugar, el vinculador controla el archivo de clave de nombre seguro mediante la especificación de ubicado en el archivo de clave... /.. /.. /.. /.. /.. / Keys/Microsoft.Practices.ESB.snk. Para editar este valor, desplácese hasta la siguiente opción:  
  
 ESB. JMS. Esquemas  
  
 Proyecto de \-  
  
 \--Propiedades  
  
 \-: Propiedades de configuración  
  
 \----Vinculador  
  
 \-----Avanzada  
  
 \------Archivo de clave  
  
> [!NOTE]
>  Si se crea un componente de canalización de JMS, debe editar el archivo AssemblyInfo.cpp para quitar todas las referencias al archivo de clave de nombre seguro, como se describió anteriormente. Después de hacerlo, editar la **archivo de clave** opción en las propiedades avanzadas del vinculador para especificar la ruta de acceso y el nombre del archivo de clave de nombre seguro.