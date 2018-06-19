---
title: Estructura de un mensaje de archivo sin formato | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00f2adf6-a47c-498b-b5ae-c6bd55bafceb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: badb8aacf6f2ed8ce9e38f1ea6bbe432a1d3b89e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278940"
---
# <a name="structure-of-a-flat-file-message"></a>Estructura de un mensaje de archivo sin formato
En el contexto de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], un mensaje de instancia de archivo sin formato es un archivo de texto que puede contener tres partes lógicas: un encabezado, un cuerpo y un finalizador, en ese orden. Tanto el encabezado como el finalizador son opcionales. En el siguiente ejemplo se muestra un mensaje de instancia de archivo sin formato formado por tres partes, donde el cuerpo aparece en negrita.  
  
```  
Microsoft Corporation  
One Microsoft Way  
Redmond, WA 98033  
  
TRANSACTION-1111,1  
  
```  
  
 Para que el desensamblador de archivos sin formato distinga correctamente el encabezado, el cuerpo y el finalizador de un mensaje de instancia de archivo sin formato, es necesario crear y configurar un esquema independiente para cada uno de ellos.  
  
 Dentro de una parte concreta de un mensaje de instancia de archivo sin formato, los distintos elementos de datos se agrupan en registros, que pueden contener subregistros y, en última instancia, los elementos individuales de datos a los que se conoce como campos. Estos registros y campos se distinguen unos de otros mediante dos metodologías básicas. La primera metodología, conocida como posicional, define cada elemento de datos para que tenga una longitud preestablecida; se utilizan caracteres controladores para que los elementos de datos más cortos tengan la longitud esperada. La segunda metodología, conocida como delimitada, utiliza uno o varios caracteres especiales para separar los elementos de datos entre sí. Esta metodología evita tener que usar caracteres controladores superfluos que de otro modo son necesarios, pero requiere que se tengan en cuenta una serie de cuestiones especiales cuando los propios datos contienen el carácter o la secuencia de caracteres utilizados como delimitador.  
  
 En el resto de la sección se ofrece información general avanzada acerca de cómo BizTalk Server trata los encabezados, los cuerpos y los finalizadores de los mensajes de instancias de archivo sin formato y, en concreto, cómo decide si las partes opcionales están presentes y cómo separa las partes de los mensajes entrantes de instancias de archivo sin formato y las combina. También contiene información adicional acerca de las diferencias entre los mensajes de instancia de archivo sin formato que utilizan registros y campos posicionales y los que emplean registros y campos delimitados.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Encabezados de mensaje de archivo sin formato](../core/flat-file-message-headers.md)  
  
-   [Cuerpos de mensaje de archivo sin formato](../core/flat-file-message-bodies.md)  
  
-   [Finalizadores de mensaje de archivo sin formato](../core/flat-file-message-trailers.md)  
  
-   [Mensajes de archivo sin formato con registros posicionales](../core/flat-file-messages-with-positional-records.md)  
  
-   [Mensajes de archivo sin formato con registros delimitados](../core/flat-file-messages-with-delimited-records.md)  
  
-   [Migrar registros de archivo sin formato](../core/migrating-flat-file-records.md)