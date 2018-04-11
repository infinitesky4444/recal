# recal

A minimal, accessible React calendar component using modern CSS, for modern browsers. It works with native Javascript dates, so there's no need to import any heavy dependencies like `moment`. For a set of functions for working with Javascript Dates, we recommend [`date-fns`](https://date-fns.org).


[**See a Live Demo**](https://rubencodes.github.io/recal)

## Installation
Using recal is simple. Just install the npm package:

```
npm i -S recal
```

## Usage

Once you've installed the package, import the necessary files into project you wish to use it in.

```
import React from 'react';

// Calendar component and enum of valid types.
import { DatePicker, DateRangePicker } from 'recal';

// Stylesheet for recal Calendar.
import 'recal/lib/index.css';
```

### Date Picker

To create a single date picker, use the `Calendar` component as follows:

```
class MyDatePicker extends React.Component {
  state = {};

  onDateSelected = (selectedDate) => {
    this.setState({
      selectedDate
    });
  }

  render() {
    return (
      <DatePicker
        date={ this.state.selectedDate }
        onDateSelected={ this.onDateSelected } />
    );
  }
}
```

### Date Range Picker

To create a date range picker, use the `Calendar` component as follows:

```
class MyDateRangePicker extends React.Component {
  state = {};

  onStartDateSelected = (startDate) => {
    this.setState({
      startDate
    });
  }
  onEndDateSelected = (endDate) => {
    this.setState({
      endDate
    });
  }

  render() {
    return (
      <DateRangePicker
        startDate={ this.state.startDate }
        endDate={ this.state.endDate }
        onStartDateSelected={ this.onStartDateSelected } />
        onEndDateSelected={ this.onEndDateSelected } />
    );
  }
}
```

### Options

Both calendars have some required and some optional props.

```
// Used by DatePicker
selectedDate: PropTypes.instanceOf(Date),
onDateSelected: PropTypes.func,

// Used by DateRangePicker
startDate: PropTypes.instanceOf(Date),
endDate: PropTypes.instanceOf(Date),
onStartDateSelected: PropTypes.func,
onEndDateSelected: PropTypes.func,

// Used by either (optional)
onDateHovered: PropTypes.func,
onDateFocused: PropTypes.func,
isDateHighlighted: PropTypes.func,
isDateEnabled: PropTypes.func,
locale: PropTypes.string
```

## Localization

Use the `locale` string prop on the calendar components to localize them into other languages *(e.g. "en-US", "es-MX", etc.)*.

## Accessibility

This set of calendars are optimized for screen readers as well as for keyboard-based navigation. The following shortcuts are available when the calendar is focused:

- Left Arrow key to navigate back 1 day,
- Right Arrow key to navigate forward 1 day,
- Up Arrow key to navigate back 1 week,
- Down Arrow key to navigate forward 1 week,
- Page Up key to navigate back 1 month,
- Page Down key to navigate forward 1 month,
- Shift + Page Up key to navigate back 1 year,
- Shift + Page Down key to navigate forward 1 year.
