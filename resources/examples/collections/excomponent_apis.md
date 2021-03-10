## Exposed Components of code null default components

## code null checkbox

**Short ID:** C0001_C1

**Version:** 1.0.0.0

**Selector:** codn-checkbox-in

### isChecked

**Type:** Method

**Description:**

Gets the checked state of the checkbox.

**Expects:**

None

**Returns:**

| Parameter | Type    | Description                       |
| --------- | ------- | --------------------------------- |
| checked   | boolean | The checked state of the checkbox |

### Label

**Type:** Value between anchor tags

**Description:**

Defines the label for the checkbox

**Expects:** string

**Required:** true

### checked

**Type:** Attribute

**Description:**

Attribute to have checkbox checked by default.

**Expects:** None, presence is sufficient.

**Required:** false

## code null radio button

**Short ID:** C0001_C2

**Version:** 1.1.0.0

**Selector:** codn-radio-in

### renderRadioButtons

**Type:** Method

**Description:**

Renders the radio buttons

**Expects:**

| Parameter | Type        | Description            | Required |
| --------- | ----------- | ---------------------- | -------- |
| data      | [radioData] | An array of radio data | true     |

**Returns:**

| Parameter | Type    | Description                       |
| --------- | ------- | --------------------------------- |
| checked   | boolean | The checked state of the checkbox |

### getSelected

**Type:** Method

**Description:**

Get the value of the selected radio button

**Expects:**

none

**Returns:**

| Parameter | Type   | Description                            |
| --------- | ------ | -------------------------------------- |
| value     | string | The value of the selected radio button |

### unselectAll

**Type:** Method

**Description:**

Unselects all radio buttons. Useful for resetting a form, if no default value is needed.

**Expects:**

none

**Returns:**

none

### Type Definitions

#### radioData

**Type:** JavaScript Object

**Description:**

Holds all the data to render a radio button.

**Structure:**

| Field   | Type    | Required | Description                                                                         |
| ------- | ------- | -------- | ----------------------------------------------------------------------------------- |
| label   | string  | true     | The label for the radio button                                                      |
| value   | string  | true     | The value for the radio button                                                      |
| checked | boolean | false    | Whether or not the radio button should be selected by default (only one in a group) |
