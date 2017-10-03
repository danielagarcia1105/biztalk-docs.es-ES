---
title: Control de cadena Values2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- string values, configuring
- formatting strings
- strings, formatting
- left-justified string values
- jdearglist.txt
- strings, left-justified
- right-justified string values
- strings, right-justified
ms.assetid: 23d54731-b2b9-4610-a533-e041237e0bb3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 024663faa56d92361d861a61a0d64a4608839aa6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="handling-string-values"></a>Control de valores de cadena
En este tema se describe cómo configurar ciertos argumentos de cadena como justificado a la derecha (y relleno a la izquierda).  
  
## <a name="types-of-string-values"></a>Tipos de valores de cadena  
 JD Edwards EnterpriseOne expone dos tipos de valores de cadena a través de su capa de interoperabilidad:  
  
-   Char: un único carácter  
  
-   cadena de longitud máxima  
  
 JD Edwards EnterpriseOne usa la notación en húngaro para asignar nombre a los argumentos de estos tipos en las funciones empresariales. Por ejemplo, los argumentos de estos tipos de comenzar con:  
  
-   c  
  
-   sz  
  
### <a name="left-justified-values"></a>Valores justificados a la izquierda  
 Para la mayoría de argumentos de tipo sz, la cadena de longitud máxima o la matriz char, JD Edwards EnterpriseOne espera un valor justificado a la izquierda. Por ejemplo, para una línea de dirección postal, que tiene una longitud máxima de 40, JD Edwards EnterpriseOne espera (por ejemplo):  
  
 "4567 Main St.       "  
  
 relleno hasta completar la longitud 40 con espacios en blanco. No es necesario que escriba el relleno porque el Adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne lo proporciona automáticamente. solo tiene que escribir "4567 Main St" en el código del cliente.  
  
### <a name="right-justified-values"></a>Valores justificados a la derecha  
 Para algunos subconjuntos de valores para este tipo, JD Edwards EnterpriseOne espera valores que están justificados a la derecha con relleno en la izquierda. Por ejemplo, para las funciones de negocio en el módulo de origen B4200310, el argumento szBusinessUnit es de longitud 12. Este argumento representa una planta, como una instalación de producción. Para un número de plantas de 30, JD Edwards EnterpriseOne espera un valor de:  
  
 "           30"  
  
 Para especificar un valor que estará justificado a la derecha, debe especificar el parámetro en un archivo denominado jdearglist.txt. El archivo jdearglist.txt se lee al generar el esquema. Cualquier valor de este archivo de texto se convierte automáticamente en un valor justificado a la derecha y relleno a la izquierda con espacios en blanco.  
  
 Debe crear jdearglist.txt usando un editor de texto, con entradas que describen estos parámetros, y guardarlo en la siguiente carpeta:  
  
 C:\Program Files\Microsoft BizTalk Adapters\JDEEnterpriseOne\config  
  
 Si este archivo no existe o está vacío, aparecerá un mensaje informativo en el registro del Adaptador de BizTalk para JD Edwards EnterpriseOne la primera vez que se abre el adaptador.  
  
> [!NOTE]
>  Si cambia este archivo después de la generación del esquema, deberá volver a generar el esquema para actualizar los datos que contiene. Para verificar que está usando la información más reciente de este archivo, puede usar el Administrador de tareas para detener el proceso browsingagent.exe antes de regenerar el esquema; no obstante, esto no debería ser necesario.  
  
 A continuación  se muestra un ejemplo del formato para entradas del archivo jdearglist.txt:  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
  
```  
  
 Por ejemplo:  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 Para un conjunto de funciones empresariales que pertenezcan al mismo módulo empresarial, los argumentos con nombre similar (del mismo tipo) se comparten entre algunas o todas las funciones empresariales. Puede usar el carácter comodín (*) en lugar del nombre de la función empresarial. Por ejemplo:  
  
```  
B4200310.*.szBusinessUnit  
  
```  
  
> [!NOTE]
>  Al importar un proceso empresarial de JD Edwards EnterpriseOne a otro equipo, debe copiar manualmente jdearglist.txt.  
  
## <a name="see-also"></a>Vea también  
 [Apéndice B: tipos de datos](../core/appendix-b-data-types.md)