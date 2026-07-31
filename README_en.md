# Excel2MaiMLData

<br/>

# A. Overview

**Excel2MaiMLData** is a program that generates a MaiML data file of type `maimlRootType` by merging:

* a MaiML file describing the experimental plan (e.g., measurement procedures and conditions), and
* an Excel file containing the experimental results obtained according to that plan.

# B. Usage

## Input and Output Files

### Input Files

#### 1. MaiML File

The input MaiML file is determined depending on whether a command-line argument is provided.

* **Without command-line arguments**

  * `/INPUT/maiml/` + the MaiML filename specified in `USERS/usersettings.py`
* **With command-line arguments**

  * The single MaiML file located in the directory specified by the argument.

#### 2. Excel File

The input Excel file is determined depending on whether a command-line argument is provided.

* **Without command-line arguments**

  * `/INPUT/excel/` + the Excel filename specified in `USERS/usersettings.py`
* **With command-line arguments**

  * The single Excel file located in the directory specified by the argument.

The required Excel format is described in:

```
settings/ExcelFormat.xlsx
```

#### 3. External Files

External files to be embedded into the generated MaiML file as `<insertion>` elements.

* **Without command-line arguments**

  * `/INPUT/others/` + the external filename specified in the Excel file.
* **With command-line arguments**

  * `<specified_directory>/` + the external filename specified in the Excel file.

---

### Output File

#### Merged MaiML File

The output path depends on whether a command-line argument is provided.

* **Without command-line arguments**

  * `OUTPUT/` + the filename specified by `_MaiML_FILENAME` in `USERS/usersettings.py`
* **With command-line arguments**

  * `<specified_directory>/` + `<input_MaiML_filename>_output.maiml`

---

## Running the Program

### Method 1: Run without Command-line Arguments

#### 1. Prepare the Input Files

* Edit the input file settings (`_INPUT_MaiML_PATH` and `_IN_EXCEL_FILENAME`) in `USERS/usersettings.py`.
* Place the MaiML file, Excel file, and external files in their corresponding input directories.

#### 2. Execute

```sh
python excel2dataMaiML.py
```

or

```sh
python excel2dataMaiML2.py
```

---

### Method 2: Run with a Directory Argument

#### 1. Prepare the Input Files

Place the following files in:

```
/INPUT/XXXXX/
```

where `XXXXX` is an arbitrary directory name.

* MaiML file
* Excel file
* External files to be inserted

#### 2. Execute

```sh
python excel2dataMaiML2.py XXXXX
```

# C. Python Environment

## Python Version

Python 3.9 or later

Ensure that Python is available in your system PATH.

## Required Python Packages

Install the packages listed in:

```
settings/requirements.txt
```

# D. Running the Sample

## 1. Confirm that the sample input files exist

The following files should be located in:

```
/INPUT/test/
```

* input.xlsx
* input.maiml
* Axoneme-56.008.tif
* test.txt

## 2. Execute

```sh
python excel2protocolMaiML2.py test
```

## 3. Verify the Output

Confirm that the following file has been generated in:

```
/INPUT/test/
```

* input_output.maiml
