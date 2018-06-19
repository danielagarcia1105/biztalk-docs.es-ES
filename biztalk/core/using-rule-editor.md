---
title: Mediante el Editor de reglas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Rule Editor [Business Rule Composer], about Rule Editor
- Rule Editor [Business Rule Composer], Conditions Editor
- Business Rule Composer, Rule Editor
- Rule Editor [Business Rule Composer], Actions Editor
- Rule Editor [Business Rule Composer]
ms.assetid: 6559a8d1-6caf-4c6e-ac80-acaa4eb57938
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57041914d688b8d0dbe2bd0558e8572878218164
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289012"
---
# <a name="using-rule-editor"></a>Usar el Editor de reglas
Utilice el Editor de reglas para ver y editar las condiciones en el Editor de condiciones y las acciones en el Editor de acciones para la regla seleccionada.  
  
## <a name="conditions-editor"></a>Editor de condiciones  
 Utilice el Editor de condiciones (parte del Editor de reglas) para ver y editar las condiciones para la activación de reglas. Asimismo, puede agregar predicados integrados mediante el menú contextual, arrastrar elementos desde el Explorador de hechos para definir argumentos y predicados, y especificar valores de argumentos en línea al hacer clic en un vínculo de argumento.  
  
 Use el menú contextual para obtener acceso a las siguientes opciones.  
  
|Use|Para|  
|--------------|----------------|  
|**Agregar operador lógico AND**|Agregar un operador para combinar dos o más predicados y formar una operación lógica **AND** expresión.|  
|**Agregar operador lógico OR**|Agregar un operador para combinar dos o más predicados y formar una operación lógica **OR** expresión.|  
|**Agregar operador lógico NOT**|Agregar el operador **no** para negar una expresión lógica o predicado.|  
|**Predicados**|Agregar una expresión de predicado basada en uno de los predicados integrados proporcionados por el modelo de objeto de regla, como el **es igual a** operador.|  
|**Predicados \ después de**|Representar el predicado temporal que responde a la pregunta "¿Es el tiempo1 cronológicamente posterior al tiempo2?".|  
|**Predicados \ antes**|Representar el predicado temporal que responde a la pregunta "¿Es el tiempo1 cronológicamente anterior al tiempo2?".|  
|**Predicados \ entre**|Representar el predicado temporal que responde a la pregunta "¿Está el tiempo1 cronológicamente entre el tiempo2 y el tiempo3?".|  
|**Predicados \ igual**|Representar el operador relacional de igualdad.|  
|**Predicados \ existe**|Representar el predicado de existencia de elemento o atributo XML utilizado en las condiciones de reglas.|  
|**Predicados \ GreaterThan**|Representar el operador relacional mayor que.|  
|**Predicados \ Predicados\mayorqueigual**|Representar el operador relacional mayor que o igual a.|  
|**Predicados \ LessThan**|Representar el operador relacional menor que.|  
|**Predicados \ Menorqueigual**|Representar el operador relacional menor que o igual a.|  
|**Predicados \ coincidencia**|Determinar si hay una expresión regular en una cadena de entrada especificada.|  
|**Predicados \ NotEqual**|Representar el operador relacional de desigualdad.|  
|**Predicados \ intervalo**|Probar si un valor se encuentra dentro de un rango.|  
|**Eliminar operador lógico**|Eliminar el operador lógico seleccionado (**AND**, **OR**, o **no**).|  
|**Eliminar predicado**|Eliminar el predicado seleccionado.|  
|**Subir**|Subir el predicado una posición o un nivel.|  
|**Bajar**|Bajar el predicado una posición o un nivel.|  
|**Ir al vocabulario**|Encontrar la definición de vocabulario en el Explorador de hechos que corresponda al argumento o predicado seleccionado.|  
|**Ir al hecho de origen**|Encontrar el elemento XML, la columna de base de datos o el método .NET en el Explorador de hechos que corresponda al argumento o predicado seleccionados.|  
|**Restablecer argumento**|Eliminar el argumento seleccionado (y los argumentos anidados) y restaurar la definición inicial.|  
|**Establecido en null**|Reemplazar el argumento seleccionado por una definición constante nula.|  
|**Establecer como cadena vacía**|Reemplazar el argumento seleccionado por un valor de cadena vacía.|  
  
## <a name="actions-editor"></a>Editor de acciones  
 Utilice el Editor de acciones (parte del Editor de reglas) para ver y editar las acciones que se van a ejecutar cuando se activa una regla. Puede agregar acciones integradas mediante el menú contextual, arrastrar elementos desde el Explorador de hechos para definir acciones y argumentos, y especificar valores de argumentos en línea al hacer clic en un vínculo de argumento.  
  
|Use|Para|  
|--------------|----------------|  
|**Eliminar acción**|Eliminar la acción seleccionada.|  
|**Ir al vocabulario**|Encontrar la definición de vocabulario en el Explorador de hechos que corresponda al argumento o acción seleccionados.|  
|**Ir al hecho de origen**|Ubicar el elemento XML, la columna de la base de datos o el método .NET en el Explorador de hechos que corresponda con el argumento o acción seleccionados.|  
|**Subir**|Subir la acción una posición o un nivel.|  
|**Bajar**|Bajar la acción una posición o un nivel.|  
|**Restablecer argumento**|Eliminar el argumento seleccionado (y los argumentos anidados) y restaurar la definición inicial.|  
|**Establecido en null**|Reemplazar el argumento seleccionado por una definición constante nula.|  
|**Establecer como cadena vacía**|Reemplazar el argumento seleccionado por un valor de cadena vacía.|  
|**Funciones**|Agregar un argumento basado en una de las funciones integradas disponibles en el modelo de objeto de regla, como el **agregar** operador.|  
|**Assert**|Agregar un hecho nuevo a la memoria de trabajo de la instancia del motor de reglas.|  
|**Retirar**|Quitar un hecho de la memoria de trabajo de la instancia del motor de reglas.|  
|**RetractByType**|Quitar un hecho del tipo especificado de la memoria de trabajo de la instancia del motor de reglas.|  
|**Desactivar**|Restablecer la memoria de trabajo y la agenda de la instancia del motor de reglas.|  
|**Detener**|Terminar el procesamiento de las reglas.|  
|**Update**|Actualizar un hecho en la memoria de trabajo de la instancia del motor de reglas.|  
  
## <a name="output-window"></a>Ventana Resultados  
 Utilice la ventana Salida para ver los resultados de la ejecución de prueba de una versión de directiva seleccionada.  
  
 Use el menú contextual para obtener acceso a las siguientes opciones.  
  
|Use|Para|  
|--------------|----------------|  
|**Borrar todo**|Borrar el texto de la ventana Resultados.|  
|**Copiar**|Copiar el texto seleccionado en la ventana Resultados al Portapapeles.|  
|**Seleccionar todo**|Seleccionar todo el texto de la ventana Salida.|  
|**Guardar en archivo**|Guardar el texto de la ventana Salida en un archivo especificado.|