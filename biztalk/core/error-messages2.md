---
title: Error Messages2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- error messages, JD Edwards OneWorld adapters
- adapters [JD Edwards OneWorld adapters], error messages
- JD Edwards OneWorld adapters, error messages
ms.assetid: 9fb65d50-83c6-426e-a0d6-674800ecf70f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84b26891592162c553fb270d2d8c9482f1c2b4d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-messages"></a>mensajes de error
En la tabla siguiente se describen los mensajes de error del sistema JD Edwards OneWorld y se proporcionan las posibles correcciones para solucionarlos.  
  
|Id. de error|Posible causa/Descripción del error|Posible corrección|  
|--------------|-----------------------------------------|-------------------------|  
|**E-JDE0002**|Faltan archivos JAR de JD Edwards OneWorld.<br /><br /> Error al crear una instancia del objeto de clase para JD Edwards OneWorld Java Data Bean.|Compruebe la ruta de acceso para el repositorio.<br /><br /> Para obtener más información, consulte [tipos básicos](../core/basic-types1.md).|  
|**E JDE0027**|Faltan archivos JAR de JD Edwards OneWorld. No se puede obtener el objeto de conexión de JD Edwards OneWorld.|Compruebe la variable de entorno CLASSPATH.<br /><br /> Consulte la actualización de CLASSPATH.<br /><br /> Compruebe sus credenciales.<br /><br /> Para obtener más información, consulte [tipos básicos](../core/basic-types1.md).|  
||Faltan archivos JAR de JD Edwards OneWorld.<br /><br /> Ruta de acceso incorrecta para el repositorio.|Compruebe la ubicación de jdeinterop.ini. Compruebe la ruta de acceso para el repositorio establecido en el archivo jdeinterop.ini.<br /><br /> Debe copiar jdeinterop.ini manualmente al importar un proceso de negocio de JD Edwards OneWorld a otro equipo.|  
||No se puede obtener el objeto de conexión de JD Edwards OneWorld.|Compruebe la configuración de CLASSPATH y las credenciales de inicio de sesión|  
|**I-JDE0043**|Servidor de aplicaciones, puerto, entorno, ruta de acceso para el archivo de configuración, usuario, contraseña incorrectos.<br /><br /> Error al iniciar sesión.|Compruebe sus credenciales de inicio de sesión.<br /><br /> Para obtener más información, consulte [tipos básicos](../core/basic-types1.md).|  
|**I-JDE0048**|Si el archivo jdearglist.txt no existe o está vacío, aparece un mensaje informativo en el registro cuando se abre Microsoft BizTalk Adapter para JD Edwards OneWorld.|Actualice el archivo jdearglist.txt para especificar una lista de parámetros que se justifique automáticamente por la derecha y se rellene por la izquierda con espacios en blanco.<br /><br /> Vea [controlar los valores de cadena](../core/handling-string-values1.md).<br /><br /> Cada vez que cambie jdearglist, debe volver a generar los esquemas para ese objeto de negocio.|  
  
## <a name="see-also"></a>Vea también  
 [Apéndice A: tipos de datos](../core/appendix-a-data-types.md)   
 [Solución de problemas de JD Edwards OneWorld](../core/troubleshooting-jd-edwards-oneworld.md)