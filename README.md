Add it in your root build.gradle at the end of repositories:

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
Step 2. Add the dependency

	dependencies {
	        implementation 'com.github.AhmedAtia39:CustomCalendar:1.0.1'
	}
////////////////////////////////////////////////////////////////////////////////////////////////////

HijriDatePicker:
-----------------

                UmmalquraCalendar now = new UmmalquraCalendar();
                HijriDatePickerDialog dpd = HijriDatePickerDialog.newInstance(
                        new HijriDatePickerDialog.OnDateSetListener() {
                            @Override
                            public void onDateSet(HijriDatePickerDialog view, int year, int monthOfYear, int dayOfMonth) {
                                String date = "You picked the following date: " + dayOfMonth + "/" + (++monthOfYear) + "/" + year;
                                dateTextView.setText(date);
                            }
                        },
                        now.get(Calendar.YEAR),
                        now.get(Calendar.MONTH),
                        now.get(Calendar.DAY_OF_MONTH)
                );

                // (1/1/current year - minus 5)
                dpd.setMinDate(new UmmalquraCalendar(now.get(Calendar.YEAR)-5,0,1));
                dpd.setMaxDate(new UmmalquraCalendar());

                //Change the language to any of supported language
                dpd.setLocale(new Locale("ar"));
                assert getFragmentManager() != null;
                dpd.show(getFragmentManager(), "Datepickerdialog");
		
/////////////////////////////////////////////////////////////////////////



>> GregorianDatePicker :

 Calendar now = Calendar.getInstance();
                GregorianDatePickerDialog dpd = GregorianDatePickerDialog.newInstance(
                        new GregorianDatePickerDialog.OnDateSetListener() {
                            @Override
                            public void onDateSet(GregorianDatePickerDialog view, int year, int monthOfYear, int dayOfMonth) {
                                String date = "You picked the following date: " + dayOfMonth + "/" + (++monthOfYear) + "/" + year;
                                dateTextView.setText(date);
                            }
                        },
                        now.get(Calendar.YEAR),
                        now.get(Calendar.MONTH),
                        now.get(Calendar.DAY_OF_MONTH)
                );

                //Change the language to any of supported language
                dpd.setLocale(new Locale("ar"));
                assert getFragmentManager() != null;
                dpd.show(getFragmentManager(), "Datepickerdialog");
                
//////////////////////////////////////////////////////////////////////////////////////////

>> TimePicker : 

 Calendar now = Calendar.getInstance();
                TimePickerDialog tpd = TimePickerDialog.newInstance(
                        new TimePickerDialog.OnTimeSetListener() {
                            @Override
                            public void onTimeSet(TimePickerDialog view, int hourOfDay, int minute, int second) {
                                String hourString = hourOfDay < 10 ? "0" + hourOfDay : "" + hourOfDay;
                                String minuteString = minute < 10 ? "0" + minute : "" + minute;
                                String secondString = second < 10 ? "0" + second : "" + second;
                                String time = "You picked the following time: " + hourString + "h" + minuteString + "m" + secondString + "s";
                            }
                        },
                        now.get(Calendar.HOUR_OF_DAY),
                        now.get(Calendar.MINUTE),
                        false
                );

                tpd.setOnCancelListener(new DialogInterface.OnCancelListener() {
                    @Override
                    public void onCancel(DialogInterface dialogInterface) {
                        Log.d("TimePicker", "Dialog was cancelled");
                    }
                });
                //Change the language to any of supported language
                tpd.setLocale(new Locale("ar"));
                assert getFragmentManager() != null;
                tpd.show(getFragmentManager(), "Timepickerdialog");
                
 ////////////////////////////////////////////////////////////////////////
 
 
                
