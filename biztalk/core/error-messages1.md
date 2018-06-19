---
title: Error Messages1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
ms.assetid: db9c9634-3f4b-4b38-b3ba-388e587fccd8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80a44049c43c499ac05a8a6f296d11add934267a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241620"
---
# <a name="error-messages"></a>mensajes de error
En la tabla siguiente se describen los mensajes de error del sistema JD Edwards EnterpriseOne y se proporcionan posibles correcciones para ellos.  
  
|Id. de error|Posible causa/Descripción del error|Posible corrección|  
|--------------|-----------------------------------------|-------------------------|  
|E JDE0027|Faltan archivos JAR de JD Edwards EnterpriseOne. No se puede adquirir el objeto de conexión JD Edwards EnterpriseOne.|Compruebe sus credenciales. Compruebe la configuración de CLASSPATH y las credenciales de inicio de sesión. Consulte la variable de entorno.|  
|I-JDE0043|Servidor de aplicaciones, puerto, entorno, ruta de acceso para el archivo de configuración, usuario, contraseña incorrectos. Error de inicio de sesión.|Verifique sus credenciales de inicio de sesión. Consulte la variable de entorno.|  
|I-JDE0048|Si el archivo jdearglist.txt no existe o está vacío, aparece un mensaje informativo en el registro cuando se abre el adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne.|Actualice el archivo jdearglist.txt para especificar una lista de parámetros que se justifique automáticamente por la derecha y se rellene por la izquierda con espacios en blanco. Para obtener más información, consulte [control de valores de cadena](../core/handling-string-values2.md). Cada vez que cambie jdearglist, debe volver a generar los esquemas para ese objeto de negocio.|  
|E JDE0027|No se puede adquirir el objeto de conexión JD Edwards EnterpriseOne. Compruebe sus CLASSPATH y credenciales.|Compruebe la ubicación del jdeinterop.ini.|  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de JD Edwards EnterpriseOne](../core/troubleshooting-jd-edwards-enterpriseone.md)   
 [Referencia técnica](../core/technical-reference6.md)