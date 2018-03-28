---
title: Control de cadena Values1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- jdearglist.txt, configuring strings
- strings, left-justified
- strings, configuring
- strings, right-justified
ms.assetid: a180b818-1009-45f5-a503-d10ed7dd27fc
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f32b29b9a8688fe8402730c1db8f12e42a67bab
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="handling-string-values"></a>Control de valores de cadena
En este tema se describe cómo configurar ciertos argumentos de cadena como justificado a la derecha (y relleno a la izquierda).  
  
## <a name="types-of-string-values"></a>Tipos de valores de cadena  
 JD Edwards OneWorld muestra dos clases de valores de cadena en su capa de interoperabilidad:  
  
-   Char: un único carácter  
  
-   cadena de longitud máxima  
  
 JD Edwards OneWorld usa la notación húngara para nombrar los argumentos de estos tipos en las funciones de negocio. Por ejemplo, los argumentos de estos tipos de comenzar con:  
  
-   c  
  
-   sz  
  
### <a name="left-justified-values"></a>Valores justificados a la izquierda  
 Para una mayoría de argumentos de tipo sz, cadena de longitud máxima o matriz de caracteres, JD Edwards OneWorld espera un valor justificado a la izquierda. Para una línea de dirección de calle, cuya longitud máxima es 40, JD Edwards OneWorld espera (por ejemplo):  
  
 "4567 Main St."  
  
 relleno hasta completar la longitud 40 con espacios en blanco. No es necesario que especifique el relleno porque Microsoft BizTalk Adapter para JD Edwards OneWorld lo proporciona automáticamente. Únicamente debe escribir "4567 Main St.", en el código de cliente.  
  
### <a name="right-justified-values"></a>Valores justificados a la derecha  
 Para algunos subconjuntos de valores de este tipo, JD Edwards OneWorld espera valores justificados a la derecha con relleno a la izquierda. Por ejemplo, para las funciones de negocio en el módulo de origen B4200310, el argumento szBusinessUnit es de longitud 12. Este argumento representa una planta, como una instalación de producción. Para un número de planta de 30, J.D. Edwards OneWorld XE espera un valor de:  
  
 "          30"  
  
 Para especificar un valor que estará justificado a la derecha, debe especificar el parámetro en un archivo denominado jdearglist.txt. El archivo jdearglist.txt se lee al generar el esquema. Cualquier valor que se indique en este archivo de texto se convierte automáticamente en un valor justificado a la derecha y rellenado a la izquierda con espacios en blanco.  
  
 Debe crear jdearglist.txt usando un texto de editor, con las entradas que describen estos parámetros y guárdelo en la siguiente carpeta: %BizTalk_Install_Adapter%\config\JDE\  
  
 Donde **BizTalk_Install_Adapter %** es el directorio en el que instaló el adaptador de BizTalk para JD Edwards OneWorld.  
  
 Si este archivo no existe o está vacío, aparece un mensaje informativo en el registro de BizTalk Adapter para JD Edwards OneWorld cuando se abre el adaptador por primera vez.  
  
> [!NOTE]
>  Si cambia este archivo después de la generación del esquema, deberá volver a generar el esquema para actualizar los datos que contiene.  
  
 Para verificar que está usando la información más reciente de este archivo, puede usar el Administrador de tareas para detener el proceso browsingagent.exe antes de regenerar el esquema; no obstante, esto no debería ser necesario.  
  
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
>  Al importar un proceso de negocio de JD Edwards OneWorld a otro equipo, debe copiar jdearglist.txt manualmente.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de justificación de cadena en Jdearglist](../core/setting-string-justification-in-jdearglist.md)   
 [Apéndice A: Tipos de datos](../core/appendix-a-data-types.md)