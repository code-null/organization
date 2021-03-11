# Exposed Components Super Awesome Modal (SAM)

Short ID: [C1912](readme_components.md)

Version: None

## open

**Type:** Method

**Description:**

Opens the modal.

**Expects:**

| Parameter | Type      | Description                                | Required |
| --------- | --------- | ------------------------------------------ | -------- |
| data      | modaldata | Contains the data to be shown in the modal | true     |

**Returns:**

| Parameter   | Type    | Description                                                     |
| ----------- | ------- | --------------------------------------------------------------- |
| wasCanceled | boolean | Whether or not the modal was closed with a cancel button or not |

## Attribute Name

**Type:** Attribute

**Description:**

Short description goes here

**Expects:** Type Name here

**Required:** true / false

## Type Definitions

### modaldata

**Type:** Interface

**Description:**

A data type to group all required information.

**Structure:**

| Field          | Type    | Required | Description                                                                                     |
| -------------- | ------- | -------- | ----------------------------------------------------------------------------------------------- |
| title          | string  | true     | The title of the modal                                                                          |
| content        | string  | true     | What should be displayed in the modal                                                           |
| isConfirmModal | boolean | true     | Tells the component if the modal should show a confirm and cancel button or just a close button |
