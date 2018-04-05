---
title: Error Messages3 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
ms.assetid: 10ea12bb-eacb-477a-bc88-28f999e60a02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1b9dd41280593de1472cd6af57ae8d1eb9fc58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-messages"></a>mensajes de error
En la tabla siguiente se enumeran mensajes de error de las interfaces de componentes del sistema PeopleSoft Enterprise, sus descripciones y posibles correcciones.  
  
 **Mensajes de error**  
  
|Id. de error|Posible causa/Descripción del error|Posible corrección|  
|--------------|-----------------------------------------|-------------------------|  
|E-JNI0004|No hay psjoa.jar.<br /><br /> Excepción grave de Java.|Compruebe la ubicación del archivo psjoa.jar de PeopleSoft.|  
|E-PSFT0030|No hay psjoa.jar.<br /><br /> No se pudo crear una instancia de beans de interfaz de componente.|Compruebe la ubicación del archivo psjoa.jar de PeopleSoft.|  
|E-PSFT0019|Nombre de servidor erróneo.<br /><br /> No se pudo establecer la conexión con Application Server de PeopleSoft.|Compruebe el host de PeopleSoft y los parámetros de usuario.|  
|E-PSFT0024|Nombre de usuario y contraseña incorrectos.<br /><br /> Error de conexión. Mensaje de error: JavaClient es un nombre de usuario no válido o que ha escrito una contraseña incorrecta.|El nombre de usuario y la contraseña de PeopleSoft son necesarios y distinguen entre mayúsculas y minúsculas. Asegúrese de que ha introducido la información con las mayúsculas y minúsculas correctas.|  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de PeopleSoft](../core/troubleshooting-peoplesoft.md)