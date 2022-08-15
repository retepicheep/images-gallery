FROM python:3.10 as build_requirements

# Create requirements file from Pipfile
COPY Pipfile Pipfile.lock ./
RUN pip install pipenv
RUN pipenv sync
RUN pipenv run pip freeze > requirements.txt

FROM python:3.10

WORKDIR /app

EXPOSE 5050

# Copy requirements.txt file from previous stage
COPY --from=build_requirements requirements.txt ./

RUN pip install -r requirements.txt

COPY . ./

CMD ["python", "main.py"]