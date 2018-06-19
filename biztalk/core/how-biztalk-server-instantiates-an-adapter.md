---
title: Cómo BizTalk Server crea una instancia de un adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ebe7585-5939-4142-9281-990b4849e28d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b32e6e40bf39c09e747391bba51a54143fc67e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246700"
---
# <a name="how-biztalk-server-instantiates-an-adapter"></a>Cómo crea BizTalk Server una instancia de un adaptador
Cuando se inicia el servicio de BizTalk, se crean instancias de todos los adaptadores de recepción siempre y cuando tengan configuradas una o varias ubicaciones de recepción y estén activas. De forma predeterminada, no se crea ninguna instancia de un adaptador de envío hasta que el motor de mensajería quita de la cola el primer mensaje que se va a enviar mediante dicho adaptador de envío. (A veces se denomina "creación diferida".) Sin embargo, si tiene que crear una instancia de un adaptador de envío al iniciar el servicio, puede usar el **InitTransmitterOnServiceStart** capacidad del adaptador. Esto indica al motor de mensajería que cree el adaptador de envío al iniciar el servicio, en lugar de utilizar la creación diferida predeterminada. El enfoque de creación diferida predeterminada ayuda a reducir la cantidad de recursos del sistema utilizados cuando los adaptadores no están configurados en extremos.  
  
 Al crear un adaptador personalizado, se recomienda el uso de código administrado. Sin embargo, es posible utilizar componentes COM nativos. Para los componentes COM el adaptador se crea una instancia de la forma normal mediante **CoCreateInstance**.  
  
 Para código administrado, debe especificar el tipo .NET **tipo** en el archivo de configuración de la ruta de acceso de ensamblado es opcional.  
  
 Existen las siguientes opciones de implementación posibles:  
  
|Tipo de .NET|Ruta del ensamblado|Método de implementación de ensamblados|  
|---------------|-------------------|--------------------------------|  
|Specified|No se ha especificado|Copiar ensamblado al directorio o subdirectorio del producto en el directorio del producto con el mismo nombre que el ensamblado|  
|Specified|No se ha especificado|Ensamblado de la caché de ensamblados global (GAC)|  
|Specified|Specified|Copiar ensamblado al directorio especificado|  
  
 **Sugerencia de solución de problemas:** cuando se crea un adaptador mediante código administrado, si se produce un error en la creación, utilice la herramienta fuslogvw.exe para determinar si hay referencias a ensamblados que no se pueden resolver. Se trata de un error habitual.  
  
 La ilustración siguiente muestra la lógica para crear adaptadores, en función de la configuración especificada.  
  
 ![](../core/media/initializingtheadapter.gif "InitializingTheAdapter")  
  
 En la tabla siguiente se proporciona un ejemplo de cómo se pueden configurar un adaptador de recepción y un ensamblado en tiempo de ejecución.  
  
|Método de implementación de ensamblados|InboundTypeName|InboundAssemblyPath|  
|--------------------------------|---------------------|-------------------------|  
|Especificar la ubicación del ensamblado|Microsoft.Samples.MyReceiveAdapter|C:\MyAdapter\MyAdapter.dll|  
|Especificar el tipo .NET (incluir clave pública, versión e información de referencia cultural)|Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, versión = 1.0.2510.24622, Culture = neutral, PublicKeyToken = 077cf886a2d1c020|N/D|  
|Ensamblado de GAC|Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, versión = 1.0.2510.24622, Culture = neutral, PublicKeyToken = 077cf886a2d1c020|N/D|