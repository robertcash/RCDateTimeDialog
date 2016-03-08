# RCDateTimeDialog

Intro:

Created a custom Date and Time dialog to use for a personal project because unlike iOS applications, Android applications don't have date and time pickers all in one UI element. This project does use the wonderful library FancyButtons for the button in my dialog and is very quick an easy to set up here: https://github.com/medyo/Fancybuttons.

How to Use:

Using the RCDateTimeDialog is really simple and easy. Here's a quick few lines of code that demonstrates how to use it:

        Dialog timeDatePicker = new Dialog(activity);

        timeDatePicker.setContentView(R.layout.time_date_dialog);
        timeDatePicker.setTitle("Date and Time");
        DatePicker dp = (DatePicker) timeDatePicker.findViewById(R.id.datePicker1);
        dp.getCalendarView().setOnDateChangeListener(new CalendarView.OnDateChangeListener() {
            @Override
            public void onSelectedDayChange(CalendarView view, int year, int month, int dayOfMonth) {
                Log.d("tag", "the date is: year " + year + ", month " + month + ", dayOfMonth " + dayOfMonth);
            }
        });

        TimePicker tp = (TimePicker) timeDatePicker.findViewById(R.id.timePicker1);

        tp.setOnTimeChangedListener(new TimePicker.OnTimeChangedListener() {

            public void onTimeChanged(TimePicker view, int hourOfDay, int minute) {
                Log.d("tag", "minute: " + minute + " hour: " + hourOfDay);
            }
        });

        FancyButton button = (FancyButton) timeDatePicker.findViewById(R.id.okButton);
        button.setOnClickListener(new View.OnClickListener() {
            public void onClick(View v){
                timeDatePicker.dismiss();
            }
        });
        
Essentialy you just create a new dialog with the layout being an instance of RCDateTimeDialog and access the id of the UI elements within to manipulate and play with. 
