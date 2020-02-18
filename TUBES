
package main

import "fmt"

type sort struct {
	nama, nim        string
	flr, rm, tm, tgl int
  av bool
}

type Gabung [10002]sort

type data struct {
	name, nim string
	av, av2   bool
	tanggal   int
}
type time struct {
	hour [7]data
}

var Room [4][12]time
var Name string
var Data int

func main() {
	var room [4][12]time
	var hour [7]data
	var gbn Gabung
	var flr, rm, tm int
	var option, option2, option3 int
  var back bool

	fmt.Println("\tRoom Booking Application")

	exit := false
	for 1 > 0 && !(exit) {
		fmt.Print("\n====================================")
		fmt.Println("\n1. Insert")
		fmt.Println("2. View")
		fmt.Println("3. Exit")
		fmt.Print("Please select one of the options : ")
		fmt.Scan(&option)
		if option == 1 {
			fmt.Print("====================================")
			Book(&room, &hour, &Data)
		} else if option == 2 {
			fmt.Print("====================================")
			View(room, Data)
			fmt.Print("\n1. Edit")
			fmt.Print("\n2. Delete")
			fmt.Print("\n3. Sort")
			fmt.Print("\n4. Back")
			fmt.Print("\nPlease select one of the options : ")
			fmt.Scan(&option2)
			back = false
			for option2 < 1 || option2 > 4 && !(back) {
				fmt.Print("\n1. Edit")
				fmt.Print("\n2. Delete")
				fmt.Print("\n3. Sort")
				fmt.Print("\n4. Back")
				fmt.Print("\nPlease select one of the options : ")
				fmt.Scan(&option2)
			}
			back2 := false
			if option2 == 1 {
				edit(&room, flr, rm, tm)
			} else if option2 == 2 {
				delete(&room, flr, rm, tm, &Data)
			} else if option2 == 3 {
				fmt.Print("\n1. Ascending")
				fmt.Print("\n2. Descending")
				fmt.Print("\n3. Back")
				fmt.Print("\nPlease select one of the options : ")
				fmt.Scan(&option3)
				for option < 1 || option > 3 && !(back2) {
					fmt.Print("\n1. Ascending")
					fmt.Print("\n2. Descending")
					fmt.Print("\n3. Back")
					fmt.Print("\nPlease select one of the options : ")
					fmt.Scan(&option3)
				}
				if option3 == 1 {
					ascending(room, &gbn, Data)
					}else if option2 == 2 {
						descending(room, &gbn, Data)
					}
				} else if option3 == 3 {
					back2 = true
        }
			} else if option2 == 4 {
				back = true
			

		} else if option == 3 {
			exit = true
		}
	}
}

func Book(room *[4][12]time, hour *[7]data, Data *int) {
	var Name, NIM string
	var flr, rm, tm, tgl int
	var yn string
	var mark bool

	fmt.Print("\nName : ")
	fmt.Scan(&Name)
	fmt.Print("NIM  : ")
	fmt.Scan(&NIM)
	mark = false
	fmt.Print("\nInput floor 1/2 : ")
	fmt.Scan(&flr)
	for flr < 1 || flr > 2 {
		fmt.Print("Input floor 1/2 : ")
		fmt.Scan(&flr)
	}
	fmt.Print("Input room 1-10 : ")
	fmt.Scan(&rm)
	for rm < 1 || rm > 10 {
		fmt.Print("Input room 1-10 : ")
		fmt.Scan(&rm)
	}
	fmt.Print("Date            : ")
	fmt.Scan(&tgl)
	for tgl < 1 || tgl > 30 {
		fmt.Print("Date            : ")
		fmt.Scan(&tgl)
	}

	fmt.Println("\n1. 6.30-8.30")
	fmt.Println("2. 8.30-10.30")
	fmt.Println("3. 10.30-12.30")
	fmt.Println("4. 12.30-14.30")
	fmt.Println("5. 14.30-16.30")
	fmt.Print("Pick a time : ")
	fmt.Scan(&tm)
	for tm < 1 || tm > 5 {
		fmt.Println("1. 6.30-8.30")
		fmt.Println("2. 8.30-10.30")
		fmt.Println("3. 10.30-12.30")
		fmt.Println("4. 12.30-14.30")
		fmt.Println("5. 14.30-16.30")
		fmt.Print("Pick a time : ")
		fmt.Scan(&tm)
	}

	if room[flr][rm].hour[tm].av == true {
		fmt.Println("\nRoom Availability:NOT AVAILABLE")
	} else if room[flr][rm].hour[tm].av == false {

		fmt.Print("\nBook This room? select y/n : ")
		fmt.Scan(&yn)

		mark = false
		for 1 > 0 && !(mark) {
			if yn == "y" {
				room[flr][rm].hour[tm].av = true
				mark = true
				room[flr][rm].hour[tm].name = Name
				room[flr][rm].hour[tm].nim = NIM
				room[flr][rm].hour[tm].tanggal = tgl
				*Data = *Data + 1
			} else if yn == "n" {
				mark = true
			} else if yn != "y" && yn != "n" {
				fmt.Print("Book this room select y/n : ")
				fmt.Scanln(&yn)
			}
		}
	}

}

func View(room [4][12]time, Data int) {
	var flr, rm, tm int
	var found bool
	var dt int

	fmt.Print("\nData : ", Data)
	fmt.Print("\n----------")
	dt = 1
	for dt <= Data {
		flr = 1
		rm = 1
		tm = 1
		found = false
		for flr <= 2 && !(found) {
			if room[flr][rm].hour[tm].av == true && room[flr][rm].hour[tm].av2 == false {
				room[flr][rm].hour[tm].av2 = true
				dt++
				found = true
				fmt.Print("\nName    : ", room[flr][rm].hour[tm].name)
				fmt.Print("\nFloor   : ", flr)
				fmt.Print("\nRoom    : ", rm)
				fmt.Print("\nDate    : ", room[flr][rm].hour[tm].tanggal)
				switch {
				case room[flr][rm].hour[tm].tanggal == 1 || room[flr][rm].hour[tm].tanggal%7 == 1:
					fmt.Print("\nDay     : Monday")
				case room[flr][rm].hour[tm].tanggal == 2 || room[flr][rm].hour[tm].tanggal%7 == 2:
					fmt.Print("\nDay     : Tuesday")
				case room[flr][rm].hour[tm].tanggal == 3 || room[flr][rm].hour[tm].tanggal%7 == 3:
					fmt.Print("\nDate    : Wednesday, ", room[flr][rm].hour[tm].tanggal)
				case room[flr][rm].hour[tm].tanggal == 4 || room[flr][rm].hour[tm].tanggal%7 == 4:
					fmt.Print("\nDay     : Thursday")
				case room[flr][rm].hour[tm].tanggal == 5 || room[flr][rm].hour[tm].tanggal%7 == 5:
					fmt.Print("\nDay     : Friday")
				case room[flr][rm].hour[tm].tanggal == 6 || room[flr][rm].hour[tm].tanggal%7 == 6:
					fmt.Print("\nDay     : Saturday ")
				case room[flr][rm].hour[tm].tanggal == 7 || room[flr][rm].hour[tm].tanggal%7 == 0:
					fmt.Print("\nDay     : Sunday")
				}

				switch {
				case tm == 1:
					fmt.Print("\nHour    : 6.30-8.30")
				case tm == 2:
					fmt.Print("\nHour    : 8.30-10.30")
				case tm == 3:
					fmt.Print("\nHour    : 10.30-12.30")
				case tm == 4:
					fmt.Print("\nHour    : 12.30-14.30")
				case tm == 5:
					fmt.Print("\nHour    : 14.30-16.30")
				}
				fmt.Print("\n-----------------------------")
			} else {
				rm = 1
				for rm <= 10 && !(found) {
					if room[flr][rm].hour[tm].av == true && room[flr][rm].hour[tm].av2 == false {
						room[flr][rm].hour[tm].av2 = true
						dt++
						found = true
						fmt.Print("\nName    : ", room[flr][rm].hour[tm].name)
						fmt.Print("\nFloor   : ", flr)
						fmt.Print("\nRoom    : ", rm)
						fmt.Print("\nDate    : ", room[flr][rm].hour[tm].tanggal)
						switch {
						case room[flr][rm].hour[tm].tanggal == 1 || room[flr][rm].hour[tm].tanggal%7 == 1:
							fmt.Print("\nDay    : Monday")
						case room[flr][rm].hour[tm].tanggal == 2 || room[flr][rm].hour[tm].tanggal%7 == 2:
							fmt.Print("\nDay    : Tuesday")
						case room[flr][rm].hour[tm].tanggal == 3 || room[flr][rm].hour[tm].tanggal%7 == 3:
							fmt.Print("\nDay    : Wednesday")
						case room[flr][rm].hour[tm].tanggal == 4 || room[flr][rm].hour[tm].tanggal%7 == 4:
							fmt.Print("\nDay    : Thursday")
						case room[flr][rm].hour[tm].tanggal == 5 || room[flr][rm].hour[tm].tanggal%7 == 5:
							fmt.Print("\nDay    : Friday")
						case room[flr][rm].hour[tm].tanggal == 6 || room[flr][rm].hour[tm].tanggal%7 == 6:
							fmt.Print("\nDay    : Saturday")
						case room[flr][rm].hour[tm].tanggal == 7 || room[flr][rm].hour[tm].tanggal%7 == 0:
							fmt.Print("\nDay    : Sunday")
						}

						switch {
						case tm == 1:
							fmt.Print("\nHour    : 6.30-8.30")
						case tm == 2:
							fmt.Print("\nHour    : 8.30-10.30")
						case tm == 3:
							fmt.Print("\nHour    : 10.30-12.30")
						case tm == 4:
							fmt.Print("\nHour    : 12.30-14.30")
						case tm == 5:
							fmt.Print("\nHour    : 14.30-16.30")
						}
						fmt.Print("\n-----------------------------")
					} else {
						tm = 1
						for tm <= 5 && !(found) {
							if room[flr][rm].hour[tm].av == true && room[flr][rm].hour[tm].av2 == false {
								room[flr][rm].hour[tm].av2 = true
								dt++
								found = true
								fmt.Print("\nName    : ", room[flr][rm].hour[tm].name)
								fmt.Print("\nFloor   : ", flr)
								fmt.Print("\nRoom    : ", rm)
								fmt.Print("\nDate    : ", room[flr][rm].hour[tm].tanggal)
								switch {
								case room[flr][rm].hour[tm].tanggal == 1 || room[flr][rm].hour[tm].tanggal%7 == 1:
									fmt.Print("\nDay     : Monday")
								case room[flr][rm].hour[tm].tanggal == 2 || room[flr][rm].hour[tm].tanggal%7 == 2:
									fmt.Print("\nDay     : Tuesday")
								case room[flr][rm].hour[tm].tanggal == 3 || room[flr][rm].hour[tm].tanggal%7 == 3:
									fmt.Print("\nDay     : Wednesday")
								case room[flr][rm].hour[tm].tanggal == 4 || room[flr][rm].hour[tm].tanggal%7 == 4:
									fmt.Print("\nDay     : Thursday")
								case room[flr][rm].hour[tm].tanggal == 5 || room[flr][rm].hour[tm].tanggal%7 == 5:
									fmt.Print("\nDay     : Friday")
								case room[flr][rm].hour[tm].tanggal == 6 || room[flr][rm].hour[tm].tanggal%7 == 6:
									fmt.Print("\nDay     : Saturday")
								case room[flr][rm].hour[tm].tanggal == 7 || room[flr][rm].hour[tm].tanggal%7 == 0:
									fmt.Print("\nDay     : Sunday")
								}

								switch {
								case tm == 1:
									fmt.Print("\nHour    : 6.30-8.30")
								case tm == 2:
									fmt.Print("\nHour    : 8.30-10.30")
								case tm == 3:
									fmt.Print("\nHour    : 10.30-12.30")
								case tm == 4:
									fmt.Print("\nHour    : 12.30-14.30")
								case tm == 5:
									fmt.Print("\nHour    : 14.30-16.30")
								}
								fmt.Print("\n-----------------------------")
							} else {
								tm++
							}
						}
						rm++
					}
				}
				flr++
			}
		}
	}
}

func ascending(room [4][12]time, gbn *Gabung, Data int) {

	var dt, j int
  var i, min int 
  var flr, rm, tm int
	var found bool
	var temp sort

dt = 1
for dt <= Data {
  flr = 1
	rm = 1
	tm = 1
	found = false
	for flr <= 2 && !(found) {
		if room[flr][rm].hour[tm].av == true && room[flr][rm].hour[tm].av2 == false  {
      room[flr][rm].hour[tm].av = false
      gbn[dt].nama = room[flr][rm].hour[tm].name
      gbn[dt].nim = room[flr][rm].hour[tm].nim
      gbn[dt].tgl = room[flr][rm].hour[tm].tanggal
      gbn[dt].flr = flr
      gbn[dt].rm = rm
      gbn[dt].tm = tm
      gbn[dt].av = true
      dt++
			found = true
		} else {
			rm = 1
			for rm <= 10 && !(found) {
				if room[flr][rm].hour[tm].av == true && room[flr][rm].hour[tm].av2 == false  {
        room[flr][rm].hour[tm].av = false
        gbn[dt].nama = room[flr][rm].hour[tm].name
        gbn[dt].nim = room[flr][rm].hour[tm].nim
        gbn[dt].tgl = room[flr][rm].hour[tm].tanggal
        gbn[dt].flr = flr
        gbn[dt].rm = rm
        gbn[dt].tm = tm
        gbn[dt].av = true
        dt++
			  found = true
				} else {
					tm = 1
					for tm <= 5 && !(found) {
						if room[flr][rm].hour[tm].av == true && room[flr][rm].hour[tm].av2 == false  {
            room[flr][rm].hour[tm].av = false
            gbn[dt].nama = room[flr][rm].hour[tm].name
            gbn[dt].nim = room[flr][rm].hour[tm].nim
            gbn[dt].tgl = room[flr][rm].hour[tm].tanggal
            gbn[dt].flr = flr
            gbn[dt].rm = rm
            gbn[dt].tm = tm
            gbn[dt].av = true
            dt++
			    found = true
						} else {
							tm++
						}
					}
					if found != true {
						rm++
					}
				}
			}
			if found != true {
				flr++
			}
		}
	}
}
dt = 1
	for dt <= Data {
		i = dt + 1
		min = dt
		for i <= Data {
			if gbn[min].nama > gbn[i].nama {
				min = i
			}
			i++
		}
		temp = gbn[dt]
    gbn[dt] = gbn[min]
    gbn[min] = temp
    dt++
	}
  fmt.Print("Data  : ", Data)
	j = 1
	for j <= Data {
		fmt.Print("\nName  : ", gbn[j].nama)
		fmt.Print("\nNIM   : ", gbn[j].nim)
		fmt.Print("\nFloor : ", gbn[j].flr)
		fmt.Print("\nRoom  : ", gbn[j].rm)
		fmt.Print("\nDate  : ", gbn[j].tgl)
		switch {
		case gbn[j].tgl == 1 || gbn[j].tgl%7 == 1:
			fmt.Print("\nDay   : Monday")
		case gbn[j].tgl == 2 || gbn[j].tgl%7 == 2:
			fmt.Print("\nDay   : Tuesday")
		case gbn[j].tgl == 3 || gbn[j].tgl%7 == 3:
			fmt.Print("\nDay   : Wednesday")
		case gbn[j].tgl == 4 || gbn[j].tgl%7 == 4:
			fmt.Print("\nDay   : Thursday")
		case gbn[j].tgl == 5 || gbn[j].tgl%7 == 5:
			fmt.Print("\nDay   : Friday")
		case gbn[j].tgl == 6 || gbn[j].tgl%7 == 6:
			fmt.Print("\nDay   : Saturday")
		case gbn[j].tgl == 7 || gbn[j].tgl%7 == 0:
			fmt.Print("\nDay   : Sunday")
		}
		switch {
		case gbn[j].tm == 1:
			fmt.Print("\nHour  : 6.30-8.30")
		case gbn[j].tm == 2:
			fmt.Print("\nHour  : 8.30-10.30")
		case gbn[j].tm == 3:
			fmt.Print("\nHour  : 10.30-12.30")
		case gbn[j].tm == 4:
			fmt.Print("\nHour  : 12.30-14.30")
		case gbn[j].tm == 5:
			fmt.Print("\nHour  : 14.30-16.30")
		}
		fmt.Print("\n-----------------------------")
		j++
	}
}

func descending(room [4][12]time, gbn *Gabung, Data int) {

	var dt, j int
  var i, max int 
  var flr, rm, tm int
	var found bool
	var temp sort

dt = 1
for dt <= Data {
  flr = 1
	rm = 1
	tm = 1
	found = false
	for flr <= 2 && !(found) {
		if room[flr][rm].hour[tm].av == true && room[flr][rm].hour[tm].av2 == false  {
      room[flr][rm].hour[tm].av = false
      gbn[dt].nama = room[flr][rm].hour[tm].name
      gbn[dt].nim = room[flr][rm].hour[tm].nim
      gbn[dt].tgl = room[flr][rm].hour[tm].tanggal
      gbn[dt].flr = flr
      gbn[dt].rm = rm
      gbn[dt].tm = tm
      gbn[dt].av = true
      dt++
			found = true
		} else {
			rm = 1
			for rm <= 10 && !(found) {
				if room[flr][rm].hour[tm].av == true && room[flr][rm].hour[tm].av2 == false  {
        room[flr][rm].hour[tm].av = false
        gbn[dt].nama = room[flr][rm].hour[tm].name
        gbn[dt].nim = room[flr][rm].hour[tm].nim
        gbn[dt].tgl = room[flr][rm].hour[tm].tanggal
        gbn[dt].flr = flr
        gbn[dt].rm = rm
        gbn[dt].tm = tm
        gbn[dt].av = true
        dt++
			  found = true
				} else {
					tm = 1
					for tm <= 5 && !(found) {
						if room[flr][rm].hour[tm].av == true && room[flr][rm].hour[tm].av2 == false  {
            room[flr][rm].hour[tm].av = false
            gbn[dt].nama = room[flr][rm].hour[tm].name
            gbn[dt].nim = room[flr][rm].hour[tm].nim
            gbn[dt].tgl = room[flr][rm].hour[tm].tanggal
            gbn[dt].flr = flr
            gbn[dt].rm = rm
            gbn[dt].tm = tm
            gbn[dt].av = true
            dt++
			    found = true
						} else {
							tm++
						}
					}
					if found != true {
						rm++
					}
				}
			}
			if found != true {
				flr++
			}
		}
	}
  dt = 1
	for dt <= Data {
		i = dt + 1 
		temp = gbn[i]
		for i > 1 && temp > gbn[i-1] {
			gbn[i] = gbn[i-1]
			i--
		}
    gbn[i] = temp
    dt++
    }
	}

    
}

func edit(room *[4][12]time, flr, rm, tm int) {
	var nflr, nrm, ntm, ntgl int
	var Search string
	var marker, found bool

	fmt.Print("====================================")
	fmt.Print("\nSearch Name : ")
	fmt.Scan(&Search)

	flr = 1
	rm = 1
	tm = 1
	found = false
	for flr <= 2 && !(found) {
		if room[flr][rm].hour[tm].name == Search {
			found = true
		} else {
			rm = 1
			for rm <= 10 && !(found) {
				if room[flr][rm].hour[tm].name == Search {
					found = true
				} else {
					tm = 1
					for tm <= 5 && !(found) {
						if room[flr][rm].hour[tm].name == Search {
							found = true
						} else {
							tm++
						}
					}
					if found != true {
						rm++
					}
				}
			}
			if found != true {
				flr++
			}
		}
	}
	if found == true {
		fmt.Println("\nfloor : ", flr)
		fmt.Println("room  : ", rm)
		fmt.Println("Date  : ", room[flr][rm].hour[tm].tanggal)
		switch {
		case tm == 1:
			fmt.Print("hour  :  6.30-8.30")
		case tm == 2:
			fmt.Print("hour  :  8.30-10.30")
		case tm == 3:
			fmt.Print("hour  :  10.30-12.30")
		case tm == 4:
			fmt.Print("hour  :  12.30-14.30")
		case tm == 5:
			fmt.Print("hour  :  14.30-16.30")
		}
	}

	fmt.Print("\n====================================")
	fmt.Print("\nNew Floor : ")
	fmt.Scan(&nflr)
	for nflr < 1 || nflr > 2 {
		fmt.Print("\nNew Floor : ")
		fmt.Scan(&nflr)
	}
	fmt.Print("New Room  : ")
	fmt.Scan(&nrm)
	for nrm < 1 || nrm > 10 {
		fmt.Print("New Room  : ")
		fmt.Scan(&nrm)
	}
	fmt.Print("New Date  : ")
	fmt.Scan(&ntgl)
	for ntgl < 1 || ntgl > 30 {
		fmt.Print("New Date  : ")
		fmt.Scan(&ntgl)
	}
	fmt.Println("\n1. 6.30-8.30")
	fmt.Println("2. 8.30-10.30")
	fmt.Println("3. 10.30-12.30")
	fmt.Println("4. 12.30-14.30")
	fmt.Println("5. 14.30-16.30")
	fmt.Print("Pick a time : ")
	fmt.Scan(&ntm)
	for ntm < 1 || ntm > 5 {
		fmt.Println("\n1. 6.30-8.30")
		fmt.Println("2. 8.30-10.30")
		fmt.Println("3. 10.30-12.30")
		fmt.Println("4. 12.30-14.30")
		fmt.Println("5. 14.30-16.30")
		fmt.Print("Pick a time : ")
		fmt.Scan(&ntm)
	}

	marker = false
	for 1 > 0 && !(marker) {
		if room[nflr][nrm].hour[ntm].av == true {
			fmt.Print("\nRoom is NOT AVAILABLE")
			fmt.Print("\nNew Floor : ")
			fmt.Scan(&nflr)
			for nflr < 1 || nflr > 2 {
				fmt.Print("\nNew Floor : ")
				fmt.Scan(&nflr)
			}
			fmt.Print("New room  : ")
			fmt.Scan(&nrm)
			for nrm < 1 || nrm > 10 {
				fmt.Print("Newroom  : ")
				fmt.Scan(&nrm)
			}
			fmt.Print("New Date  : ")
			fmt.Scan(&ntgl)
			for ntgl < 1 || ntgl > 30 {
				fmt.Print("New Date  : ")
				fmt.Scan(&ntgl)
			}
			fmt.Println("\n1. 6.30-8.30")
			fmt.Println("2. 8.30-10.30")
			fmt.Println("3. 10.30-12.30")
			fmt.Println("4. 12.30-14.30")
			fmt.Println("5. 14.30-16.30")
			fmt.Print("Pick a time : ")
			fmt.Scan(&ntm)
			for ntm < 1 || ntm > 5 {
				fmt.Println("\n1. 6.30-8.30")
				fmt.Println("2. 8.30-10.30")
				fmt.Println("3. 10.30-12.30")
				fmt.Println("4. 12.30-14.30")
				fmt.Println("5. 14.30-16.30")
				fmt.Print("Pick a time : ")
				fmt.Scan(&ntm)
			}
		} else if room[nflr][nrm].hour[ntm].av == false {
			room[nflr][nrm].hour[ntm].av = true
			room[nflr][nrm].hour[ntm].name = room[flr][rm].hour[tm].name
			room[nflr][nrm].hour[ntm].nim = room[flr][rm].hour[tm].nim
			room[nflr][nrm].hour[ntm].tanggal = ntgl
			marker = true
			room[flr][rm].hour[tm].av = false
			room[flr][rm].hour[tm].name = " "
			room[flr][rm].hour[tm].nim = " "
			room[flr][rm].hour[tm].tanggal = 0
		}
		fmt.Print("\nName  : ", room[nflr][nrm].hour[ntm].name)
		fmt.Print("\nNIM   : ", room[nflr][nrm].hour[ntm].nim)
		fmt.Print("\nDate  : ", room[nflr][nrm].hour[ntm].tanggal)
		fmt.Print("\nFloor : ", nflr)
		fmt.Print("\nRoom  : ", nrm)
		switch {
		case ntm == 1:
			fmt.Print("\nHour  : 6.30-8.30")
		case ntm == 2:
			fmt.Print("\nHour  : 8.30-10.30")
		case ntm == 3:
			fmt.Print("\nHour  : 10.30-12.30")
		case ntm == 4:
			fmt.Print("\nHour  : 12.30-14.30")
		case ntm == 5:
			fmt.Print("\nHour  : 14.30-16.30")
		}
	}
}

func delete(room *[4][12]time, flr, rm, tm int, Data *int) {
	var yn, NIM string
	var mark, found bool
	var Search string

	fmt.Print("====================================")
	fmt.Print("\nSearch Name : ")
	fmt.Scan(&Search)

	flr = 1
	rm = 1
	tm = 1
	found = false
	for flr <= 2 && !(found) {
		if room[flr][rm].hour[tm].name == Search {
			found = true
		} else {
			rm = 1
			for rm <= 10 && !(found) {
				if room[flr][rm].hour[tm].name == Search {
					found = true
				} else {
					tm = 1
					for tm <= 5 && !(found) {
						if room[flr][rm].hour[tm].name == Search {
							found = true
						} else {
							tm++
						}
					}
					if found != true {
						rm++
					}
				}
			}
			if found != true {
				flr++
			}
		}
	}
	if found == true {
		fmt.Println("\nfloor : ", flr)
		fmt.Println("room  : ", rm)
		switch {
		case tm == 1:
			fmt.Print("hour  :  6.30-8.30")
		case tm == 2:
			fmt.Print("hour  :  8.30-10.30")
		case tm == 3:
			fmt.Print("hour  :  10.30-12.30")
		case tm == 4:
			fmt.Print("hour  :  12.30-14.30")
		case tm == 5:
			fmt.Print("hour  :  14.30-16.30")
		}
	} else {
    fmt.Print("Name is not registered")
  }
  if room[flr][rm].hour[tm].name == Search {
	fmt.Print("\nConfirm to Delete Data y/n : ")
	fmt.Scan(&yn)
  fmt.Print("\nEnter your NIM : ")
	fmt.Scan(&NIM)
	mark = false
	for 1 > 0 && !(mark) {
		if yn == "y" && room[flr][rm].hour[tm].nim == NIM {
			room[flr][rm].hour[tm].av = true
			room[flr][rm].hour[tm].av2 = true
			mark = true
			room[flr][rm].hour[tm].name = ""
			room[flr][rm].hour[tm].nim = ""
			*Data = *Data - 1
		} else if yn == "n" {
			mark = true
		} else if yn != "y" && yn != "n" {
			fmt.Print("\nConfirm to Delete Data y/n : ")
			fmt.Scanln(&yn)

			fmt.Print("\nEnter your NIM : ")
			fmt.Scan(&NIM)
    } else if room[flr][rm].hour[tm].nim != NIM { 
    fmt.Print("NIM is not registered")
    mark = true
  }
	
		}
	}
}
